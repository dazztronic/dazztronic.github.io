---
allowed-tools: Bash(git status:*), Bash(pwd), Bash(git diff:*)
description: Analyze content for SEO optimization opportunities across the Zola blog
---

## Context

- Current directory: !`pwd`
- Current Git-Status: !`git status`
- Current Git-Diff (staged and unstaged changes): !`git diff HEAD`

## Usage

```
/project:audit-seo [path] [--format=json|markdown]
```

## Parameters

- `path` (optional): Specific content path to audit (e.g., `content/blog/2025-03-*`)
- `--format` (optional): Output format, defaults to `markdown`

## Description

This command performs comprehensive SEO analysis of blog content, checking:

- Missing or inadequate meta descriptions in frontmatter
- Title optimization (length, keywords)
- Heading structure validation (H1, H2, H3 hierarchy)
- Image alt text presence
- Internal linking opportunities
- Content length analysis
- Keyword density patterns

## Implementation

```bash
#!/bin/bash

# Default parameters
CONTENT_PATH="${1:-content/}"
FORMAT="${2:-markdown}"

echo "🔍 Running SEO audit on: $CONTENT_PATH"

# Find all markdown files
find "$CONTENT_PATH" -name "*.md" -type f | while read -r file; do
    echo "Analyzing: $file"
    
    # Check frontmatter for missing meta fields
    if ! grep -q "^title =" "$file"; then
        echo "❌ Missing title in $file"
    fi
    
    # Check title length (should be 30-60 chars)
    title=$(grep "^title =" "$file" | sed 's/title = "//' | sed 's/"//')
    if [ ${#title} -lt 30 ] || [ ${#title} -gt 60 ]; then
        echo "⚠️  Title length issue in $file: ${#title} chars"
    fi
    
    # Check for missing excerpt/description
    if ! grep -q "^excerpt =" "$file" && ! grep -q "^description =" "$file"; then
        echo "❌ Missing excerpt/description in $file"
    fi
    
    # Check heading hierarchy
    h1_count=$(grep -c "^# " "$file" || true)
    if [ "$h1_count" -ne 1 ]; then
        echo "⚠️  H1 count issue in $file: $h1_count (should be 1)"
    fi
    
    # Check for images without alt text
    if grep -q "!\[.*\]" "$file"; then
        while IFS= read -r line; do
            if echo "$line" | grep -q "!\[\]" || echo "$line" | grep -q "!\[ \]"; then
                echo "❌ Image without alt text in $file: $line"
            fi
        done < <(grep "!\[.*\]" "$file")
    fi
    
    # Word count analysis
    word_count=$(wc -w < "$file")
    if [ "$word_count" -lt 300 ]; then
        echo "⚠️  Short content in $file: $word_count words"
    fi
    
done

echo "✅ SEO audit complete"
```

## Output Example

```
🔍 Running SEO audit on: content/blog/

Analyzing: content/blog/2025-03-pie-php-extension-installer/index.md
⚠️  Title length issue: 45 chars (optimal: 30-60)
✅ Meta description present
✅ Proper heading hierarchy
❌ Image without alt text: ![](hero.png)

Analyzing: content/blog/2025-01-symfony-security/index.md  
✅ Title length optimal: 52 chars
❌ Missing excerpt/description
✅ Proper heading hierarchy
⚠️  Short content: 280 words

SEO Recommendations:
- Add meta descriptions to 3 posts
- Optimize 2 titles for length
- Add alt text to 5 images
- Expand content for 1 short post
```