---
allowed-tools: Bash(pwd), Bash(git status:*), Bash(find:*), Bash(awk:*), Bash(wc:*), Glob, Read
description: Analyze and report reading times across all blog content with detailed statistics
---

## Context

- Current directory: !`pwd`
- Current Git-Status: !`git status`
- Total blog posts: !`find content/blog -name "index.md" | wc -l`
- Recent posts: !`fd -t f index.md content/blog/ | head -3`

## Usage

```
/project:audit-reading-time [--category=<name>] [--author=<name>] [--format=json|table|csv] [--export=<file>]
```

## Parameters

- `--category` (optional): Filter by specific category (e.g., "PHP", "Symfony")
- `--author` (optional): Filter by specific author name
- `--format` (optional): Output format - `table` (default), `json`, or `csv`
- `--export` (optional): Export results to file

## Description

This command provides comprehensive reading time analysis including:

- Individual post reading times with word counts
- Distribution analysis (short, medium, long content)
- Author-specific statistics
- Category-based breakdowns
- Content recommendations based on reading time
- Identification of outliers (very short or very long posts)

## Implementation

```bash
#!/bin/bash

# Default parameters
CATEGORY=""
AUTHOR=""
FORMAT="table"
EXPORT_FILE=""

# Parse arguments
while [[ $# -gt 0 ]]; do
    case $1 in
        --category=*)
            CATEGORY="${1#*=}"
            shift
            ;;
        --author=*)
            AUTHOR="${1#*=}"
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

echo "📊 Analyzing reading times for blog content..."

# Create temporary files for processing
TEMP_DATA=$(mktemp)
TEMP_STATS=$(mktemp)

# Process all blog posts
find content/blog -name "index.md" -type f | while read -r file; do
    # Extract frontmatter data
    title=$(grep "^title =" "$file" | sed 's/^title = "//' | sed 's/"$//')
    date=$(grep "^date =" "$file" | sed 's/^date = //')
    
    # Extract categories and authors from frontmatter
    categories=$(awk '/^\[taxonomies\]/,/^\[/ { if(/^categories =/) print }' "$file" | sed 's/categories = \[//' | sed 's/\]//' | tr -d '"')
    authors=$(awk '/^\[taxonomies\]/,/^\[/ { if(/^authors =/) print }' "$file" | sed 's/authors = \[//' | sed 's/\]//' | tr -d '"')
    
    # Calculate word count (excluding frontmatter)
    word_count=$(awk '/^\+\+\+$/,/^\+\+\+$/ { if (count == 1) next } /^\+\+\+$/ { count++ } count >= 2 { print }' "$file" | wc -w)
    
    # Calculate reading time (based on Medium's 265 WPM)
    reading_time=$(echo "scale=1; $word_count / 265" | bc -l)
    reading_time_rounded=$(echo "($word_count + 264) / 265" | bc)
    
    # Get directory name for slug
    slug=$(dirname "$file" | xargs basename)
    
    # Apply filters
    if [ -n "$CATEGORY" ] && ! echo "$categories" | grep -qi "$CATEGORY"; then
        continue
    fi
    
    if [ -n "$AUTHOR" ] && ! echo "$authors" | grep -qi "$AUTHOR"; then
        continue
    fi
    
    # Output data line
    echo "$slug|$title|$date|$word_count|$reading_time_rounded|$categories|$authors"
done > "$TEMP_DATA"

# Calculate statistics
total_posts=$(wc -l < "$TEMP_DATA")
if [ "$total_posts" -eq 0 ]; then
    echo "❌ No posts found matching criteria"
    rm -f "$TEMP_DATA" "$TEMP_STATS"
    exit 1
fi

total_words=$(awk -F'|' '{sum+=$4} END {print sum}' "$TEMP_DATA")
avg_words=$(echo "scale=0; $total_words / $total_posts" | bc -l)
total_reading_time=$(awk -F'|' '{sum+=$5} END {print sum}' "$TEMP_DATA")
avg_reading_time=$(echo "scale=1; $total_reading_time / $total_posts" | bc -l)

# Categorize by length
short_posts=$(awk -F'|' '$5 < 3 {count++} END {print count+0}' "$TEMP_DATA")
medium_posts=$(awk -F'|' '$5 >= 3 && $5 <= 7 {count++} END {print count+0}' "$TEMP_DATA")
long_posts=$(awk -F'|' '$5 > 7 {count++} END {print count+0}' "$TEMP_DATA")

# Generate output based on format
case $FORMAT in
    "json")
        cat << EOF
{
  "summary": {
    "total_posts": $total_posts,
    "total_words": $total_words,
    "total_reading_time_minutes": $total_reading_time,
    "average_words_per_post": $avg_words,
    "average_reading_time_minutes": $avg_reading_time,
    "distribution": {
      "short_posts_under_3min": $short_posts,
      "medium_posts_3_7min": $medium_posts,
      "long_posts_over_7min": $long_posts
    }
  },
  "posts": [
EOF
        awk -F'|' 'BEGIN{first=1} {
            if(!first) print ",";
            printf "    {\n      \"slug\": \"%s\",\n      \"title\": \"%s\",\n      \"date\": \"%s\",\n      \"word_count\": %s,\n      \"reading_time_minutes\": %s,\n      \"categories\": \"%s\",\n      \"authors\": \"%s\"\n    }", $1, $2, $3, $4, $5, $6, $7;
            first=0
        }' "$TEMP_DATA"
        echo -e "\n  ]\n}"
        ;;
    
    "csv")
        echo "slug,title,date,word_count,reading_time_minutes,categories,authors"
        sed 's/|/,/g' "$TEMP_DATA"
        ;;
        
    "table"|*)
        echo "📈 Reading Time Analysis Report"
        echo "================================"
        echo
        echo "📊 Summary Statistics:"
        echo "  Total Posts: $total_posts"
        echo "  Total Words: $total_words"
        echo "  Total Reading Time: $total_reading_time minutes"
        echo "  Average Words/Post: $avg_words"
        echo "  Average Reading Time: $avg_reading_time minutes"
        echo
        echo "📋 Content Distribution:"
        echo "  Short Posts (<3 min): $short_posts ($(echo "scale=1; $short_posts * 100 / $total_posts" | bc -l)%)"
        echo "  Medium Posts (3-7 min): $medium_posts ($(echo "scale=1; $medium_posts * 100 / $total_posts" | bc -l)%)"
        echo "  Long Posts (>7 min): $long_posts ($(echo "scale=1; $long_posts * 100 / $total_posts" | bc -l)%)"
        echo
        echo "📝 Individual Posts:"
        printf "%-30s %-8s %-6s %s\n" "TITLE" "WORDS" "TIME" "CATEGORIES"
        echo "$(printf '%.0s-' {1..70})"
        awk -F'|' '{
            title = (length($2) > 25) ? substr($2, 1, 25) "..." : $2;
            printf "%-30s %-8s %-6s %s\n", title, $4, $5 "min", $6
        }' "$TEMP_DATA" | sort -k3 -nr
        echo
        echo "💡 Recommendations:"
        if [ "$short_posts" -gt $(echo "$total_posts / 3" | bc) ]; then
            echo "  - Consider expanding short posts for better SEO and depth"
        fi
        if [ "$long_posts" -gt $(echo "$total_posts / 2" | bc) ]; then
            echo "  - Consider breaking long posts into series for better engagement"
        fi
        echo "  - Optimal reading time for engagement: 3-7 minutes"
        ;;
esac

# Export to file if requested
if [ -n "$EXPORT_FILE" ]; then
    case $FORMAT in
        "json")
            # Re-run JSON output to file
            /project:audit-reading-time --format=json > "$EXPORT_FILE"
            ;;
        "csv")
            echo "slug,title,date,word_count,reading_time_minutes,categories,authors" > "$EXPORT_FILE"
            sed 's/|/,/g' "$TEMP_DATA" >> "$EXPORT_FILE"
            ;;
        *)
            /project:audit-reading-time --format=table > "$EXPORT_FILE"
            ;;
    esac
    echo "📁 Results exported to: $EXPORT_FILE"
fi

# Cleanup
rm -f "$TEMP_DATA" "$TEMP_STATS"

echo "✅ Reading time analysis complete"
```

## Output Example

```
📊 Analyzing reading times for blog content...

📈 Reading Time Analysis Report
================================

📊 Summary Statistics:
  Total Posts: 11
  Total Words: 45,230
  Total Reading Time: 171 minutes
  Average Words/Post: 4,112
  Average Reading Time: 15.5 minutes

📋 Content Distribution:
  Short Posts (<3 min): 1 (9.1%)
  Medium Posts (3-7 min): 3 (27.3%)
  Long Posts (>7 min): 7 (63.6%)

📝 Individual Posts:
TITLE                          WORDS    TIME   CATEGORIES
---------------------------------------------------------------------- 
Symfony Microservices Arch...   8245     31min  Symfony
PHP Performance Optimizati...   6890     26min  PHP
Modern PHP Development Tool...   5234     20min  PHP
Symfony Security Implement...   4567     17min  Symfony
PHP Design Patterns             3892     15min  PHP
PIE - PHP Extension Install...   3245     12min  PHP
Symfony API Development         2876     11min  Symfony
PHP Testing Strategies          2134      8min  PHP
Symfony Doctrine Best Prac...   1987      7min  Symfony
Symfony Deployment Strateg...   1456      5min  Symfony

💡 Recommendations:
  - Consider breaking long posts into series for better engagement
  - Optimal reading time for engagement: 3-7 minutes

✅ Reading time analysis complete
```

## Usage Examples

```bash
# Analyze all posts
/project:audit-reading-time

# Filter by category
/project:audit-reading-time --category=Symfony

# Filter by author
/project:audit-reading-time --author="Anne-Julia"

# Export as JSON
/project:audit-reading-time --format=json --export=reading-times.json

# CSV export for spreadsheet analysis
/project:audit-reading-time --format=csv --export=reading-analysis.csv
```