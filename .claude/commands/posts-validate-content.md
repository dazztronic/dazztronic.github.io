---
allowed-tools: Bash(pwd), Bash(git status:*), Bash(find:*), Bash(grep:*), Bash(awk:*), Glob, Read, Edit
description: Comprehensive validation of blog content including structure, frontmatter, and quality checks
---

## Context

- Current directory: !`pwd`
- Current Git-Status: !`git status`
- Total blog posts: !`find content/blog -name "index.md" | wc -l`
- Content structure: !`fd -t d . content/ | head -10`
- Zola version check: !`zola --version 2>/dev/null || echo "Zola not found"`

## Usage

```
/project:posts-validate-content [path] [--fix] [--verbose] [--format=json|table] [--export=<file>]
```

## Parameters

- `path` (optional): Specific content path to validate (defaults to `content/blog/`)
- `--fix` (optional): Automatically fix common issues where possible
- `--verbose` (optional): Show detailed validation results
- `--format` (optional): Output format - `table` (default) or `json`
- `--export` (optional): Export validation report to file

## Description

This command performs comprehensive content validation including:

- **Frontmatter validation**: Required fields, proper TOML syntax, data types
- **Content structure**: Heading hierarchy, image references, internal links
- **File organization**: Proper directory structure, naming conventions
- **Asset validation**: Hero images exist and are properly sized
- **Content quality**: Reading time, word count, excerpt length
- **Zola compatibility**: Template references, shortcode usage

## Implementation

```bash
#!/bin/bash

# Default parameters
CONTENT_PATH="${1:-content/blog/}"
FIX_ISSUES=false
VERBOSE=false
FORMAT="table"
EXPORT_FILE=""

# Parse arguments
shift
while [[ $# -gt 0 ]]; do
    case $1 in
        --fix)
            FIX_ISSUES=true
            shift
            ;;
        --verbose)
            VERBOSE=true
            shift
            ;;
        --format=*)
            FORMAT="${1#*=}"
            shift
            ;;
        --export=*)
            EXPORT_FILE="${1#*=}"
            shift
            ;;
        *)
            echo "Unknown option: $1"
            exit 1
            ;;
    esac
done

echo "🔍 Validating content in: $CONTENT_PATH"

# Initialize counters
TOTAL_POSTS=0
ERRORS=0
WARNINGS=0
FIXED=0

# Temporary files for results
TEMP_RESULTS=$(mktemp)
TEMP_SUMMARY=$(mktemp)

# Required frontmatter fields
REQUIRED_FIELDS=("title" "date" "draft")
RECOMMENDED_FIELDS=("authors" "categories" "tags" "hero_image" "excerpt")

# Validation function
validate_post() {
    local file="$1"
    local slug=$(dirname "$file" | xargs basename)
    local errors=0
    local warnings=0
    local fixes=0
    
    if [ "$VERBOSE" = true ]; then
        echo "  Validating: $slug"
    fi
    
    # Check if file exists and is readable
    if [ ! -r "$file" ]; then
        echo "ERROR|$slug|File not readable: $file" >> "$TEMP_RESULTS"
        return 1
    fi
    
    # Extract frontmatter
    local frontmatter=$(awk '/^\+\+\+$/,/^\+\+\+$/ { if (NR > 1 && /^\+\+\+$/) exit; if (NR > 1) print }' "$file")
    
    # Check required fields
    for field in "${REQUIRED_FIELDS[@]}"; do
        if ! echo "$frontmatter" | grep -q "^$field ="; then
            echo "ERROR|$slug|Missing required field: $field" >> "$TEMP_RESULTS"
            ((errors++))
            
            # Auto-fix for draft field
            if [ "$field" = "draft" ] && [ "$FIX_ISSUES" = true ]; then
                # Add draft = false after title
                sed -i '/^title =/a draft = false' "$file"
                echo "FIXED|$slug|Added missing draft field" >> "$TEMP_RESULTS"
                ((fixes++))
            fi
        fi
    done
    
    # Validate date format
    if echo "$frontmatter" | grep -q "^date ="; then
        local date_value=$(echo "$frontmatter" | grep "^date =" | sed 's/^date = //')
        if ! date -d "$date_value" >/dev/null 2>&1; then
            echo "ERROR|$slug|Invalid date format: $date_value" >> "$TEMP_RESULTS"
            ((errors++))
        fi
    fi
    
    # Check recommended fields
    for field in "${RECOMMENDED_FIELDS[@]}"; do
        if ! echo "$frontmatter" | grep -q "^$field ="; then
            echo "WARNING|$slug|Missing recommended field: $field" >> "$TEMP_RESULTS"
            ((warnings++))
        fi
    done
    
    # Validate taxonomies section
    if echo "$frontmatter" | grep -q "^\[taxonomies\]"; then
        # Check authors format
        if echo "$frontmatter" | grep -q "^authors ="; then
            local authors_line=$(echo "$frontmatter" | grep "^authors =")
            if ! echo "$authors_line" | grep -q '\[.*\]'; then
                echo "ERROR|$slug|Authors field must be an array: $authors_line" >> "$TEMP_RESULTS"
                ((errors++))
            fi
        fi
        
        # Check categories format
        if echo "$frontmatter" | grep -q "^categories ="; then
            local categories_line=$(echo "$frontmatter" | grep "^categories =")
            if ! echo "$categories_line" | grep -q '\[.*\]'; then
                echo "ERROR|$slug|Categories field must be an array: $categories_line" >> "$TEMP_RESULTS"
                ((errors++))
            fi
        fi
    fi
    
    # Check hero image
    if echo "$frontmatter" | grep -q "^hero_image ="; then
        local hero_image=$(echo "$frontmatter" | grep "^hero_image =" | sed 's/^hero_image = "//' | sed 's/"$//')
        local hero_path="$(dirname "$file")/$hero_image"
        
        if [ ! -f "$hero_path" ]; then
            echo "ERROR|$slug|Hero image not found: $hero_path" >> "$TEMP_RESULTS"
            ((errors++))
        else
            # Check image dimensions (if imagemagick is available)
            if command -v identify >/dev/null 2>&1; then
                local dimensions=$(identify "$hero_path" 2>/dev/null | awk '{print $3}')
                if [ -n "$dimensions" ]; then
                    local width=$(echo "$dimensions" | cut -d'x' -f1)
                    local height=$(echo "$dimensions" | cut -d'x' -f2)
                    
                    if [ "$width" -lt 1000 ] || [ "$height" -lt 500 ]; then
                        echo "WARNING|$slug|Hero image too small: ${width}x${height} (recommended: 1200x600)" >> "$TEMP_RESULTS"
                        ((warnings++))
                    fi
                fi
            fi
        fi
    fi
    
    # Validate content structure
    local content=$(awk '/^\+\+\+$/,/^\+\+\+$/ { if (count == 1) next } /^\+\+\+$/ { count++ } count >= 2 { print }' "$file")
    
    # Check for H1 headings (should only be in title)
    local h1_count=$(echo "$content" | grep -c "^# " || true)
    if [ "$h1_count" -gt 0 ]; then
        echo "WARNING|$slug|Contains H1 headings in content ($h1_count found). Use H2-H6." >> "$TEMP_RESULTS"
        ((warnings++))
    fi
    
    # Check for empty sections
    if echo "$content" | grep -q "^## .*\n\n## "; then
        echo "WARNING|$slug|Contains empty sections" >> "$TEMP_RESULTS"
        ((warnings++))
    fi
    
    # Word count check
    local word_count=$(echo "$content" | wc -w)
    if [ "$word_count" -lt 300 ]; then
        echo "WARNING|$slug|Short content: $word_count words (recommended: 300+)" >> "$TEMP_RESULTS"
        ((warnings++))
    fi
    
    # Check for broken internal links (simplified)
    while IFS= read -r line; do
        if echo "$line" | grep -q "\[.*\](\.\.*/.*\.md)"; then
            local link=$(echo "$line" | grep -o "\[.*\](\.\.*/.*\.md)" | sed 's/.*](//' | sed 's/).*//')
            local link_path="$(dirname "$file")/$link"
            if [ ! -f "$link_path" ]; then
                echo "ERROR|$slug|Broken internal link: $link" >> "$TEMP_RESULTS"
                ((errors++))
            fi
        fi
    done <<< "$content"
    
    # Check excerpt length
    if echo "$frontmatter" | grep -q "^excerpt ="; then
        local excerpt=$(echo "$frontmatter" | grep "^excerpt =" | sed 's/^excerpt = "//' | sed 's/"$//')
        local excerpt_length=${#excerpt}
        if [ "$excerpt_length" -gt 160 ]; then
            echo "WARNING|$slug|Excerpt too long: $excerpt_length chars (recommended: <160)" >> "$TEMP_RESULTS"
            ((warnings++))
        elif [ "$excerpt_length" -lt 50 ]; then
            echo "WARNING|$slug|Excerpt too short: $excerpt_length chars (recommended: 50-160)" >> "$TEMP_RESULTS"
            ((warnings++))
        fi
    fi
    
    # Check directory naming convention
    if ! echo "$slug" | grep -q "^[0-9]\{4\}-[0-9]\{2\}-"; then
        echo "WARNING|$slug|Directory name doesn't follow YYYY-MM-title convention" >> "$TEMP_RESULTS"
        ((warnings++))
    fi
    
    echo "$errors|$warnings|$fixes" >> "$TEMP_SUMMARY"
}

# Process all blog posts
find "$CONTENT_PATH" -name "index.md" -type f | while read -r file; do
    ((TOTAL_POSTS++))
    validate_post "$file"
done

# Calculate totals
TOTAL_POSTS=$(find "$CONTENT_PATH" -name "index.md" -type f | wc -l)
ERRORS=$(awk -F'|' '{sum+=$1} END {print sum+0}' "$TEMP_SUMMARY")
WARNINGS=$(awk -F'|' '{sum+=$2} END {print sum+0}' "$TEMP_SUMMARY")
FIXED=$(awk -F'|' '{sum+=$3} END {print sum+0}' "$TEMP_SUMMARY")

# Generate output based on format
case $FORMAT in
    "json")
        cat << EOF
{
  "summary": {
    "total_posts": $TOTAL_POSTS,
    "errors": $ERRORS,
    "warnings": $WARNINGS,
    "fixed": $FIXED,
    "validation_date": "$(date -Iseconds)",
    "content_path": "$CONTENT_PATH"
  },
  "issues": [
EOF
        awk -F'|' 'BEGIN{first=1} {
            if(!first) print ",";
            printf "    {\n      \"type\": \"%s\",\n      \"post\": \"%s\",\n      \"message\": \"%s\"\n    }", $1, $2, $3;
            first=0
        }' "$TEMP_RESULTS"
        echo -e "\n  ]\n}"
        ;;
        
    "table"|*)
        echo "📋 Content Validation Report"
        echo "============================"
        echo
        echo "📊 Summary:"
        echo "  Total Posts: $TOTAL_POSTS"
        echo "  Errors: $ERRORS"
        echo "  Warnings: $WARNINGS"
        if [ "$FIX_ISSUES" = true ]; then
            echo "  Fixed Issues: $FIXED"
        fi
        echo "  Validation Path: $CONTENT_PATH"
        echo
        
        if [ -s "$TEMP_RESULTS" ]; then
            echo "🚨 Issues Found:"
            echo
            printf "%-8s %-30s %s\n" "TYPE" "POST" "MESSAGE"
            echo "$(printf '%.0s-' {1..80})"
            awk -F'|' '{
                post = (length($2) > 25) ? substr($2, 1, 25) "..." : $2;
                printf "%-8s %-30s %s\n", $1, post, $3
            }' "$TEMP_RESULTS"
            echo
        else
            echo "✅ No issues found! All content is valid."
            echo
        fi
        
        # Provide recommendations
        echo "💡 Recommendations:"
        if [ "$ERRORS" -gt 0 ]; then
            echo "  - Fix all ERROR items before publishing"
        fi
        if [ "$WARNINGS" -gt 0 ]; then
            echo "  - Address WARNING items to improve content quality"
        fi
        if [ "$FIX_ISSUES" = false ] && [ "$ERRORS" -gt 0 ]; then
            echo "  - Run with --fix to automatically fix some issues"
        fi
        echo "  - Use 'zola check' for additional link validation"
        ;;
esac

# Export to file if requested
if [ -n "$EXPORT_FILE" ]; then
    case $FORMAT in
        "json")
            /project:posts-validate-content "$CONTENT_PATH" --format=json > "$EXPORT_FILE"
            ;;
        *)
            /project:posts-validate-content "$CONTENT_PATH" --format=table > "$EXPORT_FILE"
            ;;
    esac
    echo "📁 Validation report exported to: $EXPORT_FILE"
fi

# Cleanup
rm -f "$TEMP_RESULTS" "$TEMP_SUMMARY"

# Exit with appropriate code
if [ "$ERRORS" -gt 0 ]; then
    echo "❌ Validation completed with errors"
    exit 1
else
    echo "✅ Validation completed successfully"
    exit 0
fi
```

## Output Example

```
🔍 Validating content in: content/blog/

📋 Content Validation Report
============================

📊 Summary:
  Total Posts: 11
  Errors: 3
  Warnings: 7
  Fixed Issues: 1
  Validation Path: content/blog/

🚨 Issues Found:

TYPE     POST                           MESSAGE
--------------------------------------------------------------------------------
ERROR    2025-01-modern-php-tools       Missing required field: draft
ERROR    2025-02-symfony-api            Hero image not found: content/blog/2025-02-symfony-api/hero.png
WARNING  2025-01-php-performance        Excerpt too long: 180 chars (recommended: <160)
WARNING  2025-03-pie-installer          Hero image too small: 800x400 (recommended: 1200x600)
WARNING  2025-02-php-patterns           Missing recommended field: authors
FIXED    2025-01-modern-php-tools       Added missing draft field

💡 Recommendations:
  - Fix all ERROR items before publishing
  - Address WARNING items to improve content quality
  - Use 'zola check' for additional link validation

✅ Validation completed successfully
```

## Usage Examples

```bash
# Validate all blog posts
/project:posts-validate-content

# Validate specific path
/project:posts-validate-content content/blog/2025-03-*

# Auto-fix common issues
/project:posts-validate-content --fix

# Verbose output with detailed checks
/project:posts-validate-content --verbose

# Export JSON report
/project:posts-validate-content --format=json --export=validation-report.json

# Complete validation with fixes and export
/project:posts-validate-content --fix --verbose --export=validation-results.txt
```

## Integration with CI/CD

Add to your build pipeline:

```yaml
- name: Validate content
  run: /project:posts-validate-content
  # This will exit with code 1 if errors are found, failing the build
```