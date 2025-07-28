+++
title = "UI Components"
template = "page.html"
+++

This page demonstrates the various UI components available for use in blog posts and content.

## Admonitions

Admonitions are special callout boxes that can be used to highlight important information, warnings, tips, and more.

{% note(title="Note") %}
This is a note admonition. Use it for general information that readers should be aware of.
{% end %}

{% info(title="Information") %}
This is an info admonition. Use it to provide additional context or explanatory information.
{% end %}

{% tip(title="Pro Tip") %}
This is a tip admonition. Use it to share helpful advice or best practices with your readers.
{% end %}

{% success(title="Success") %}
This is a success admonition. Use it to highlight positive outcomes or successful completions.
{% end %}

{% warning(title="Warning") %}
This is a warning admonition. Use it to alert readers about potential issues or things to be careful about.
{% end %}

{% danger(title="Danger") %}
This is a danger admonition. Use it for critical warnings about things that could cause serious problems.
{% end %}

{% example(title="Code Example") %}
This is an example admonition. Use it to showcase code snippets, usage examples, or demonstrations.
{% end %}

{% quote(title="Quote") %}
This is a quote admonition. Use it for highlighting quotes, testimonials, or important statements from others.
{% end %}

### Usage

To use these admonitions in your blog posts, use the shortcode syntax:

````markdown
{% note(title="Important Note") %}
This is the content of the note. You can use **markdown** here.
{% end %}

{% warning(title="Be Careful") %}
This is a warning message with important information.
{% end %}

{% tip() %}
You can omit the title to use the default title.
{% end %}
````

### Available Shortcodes
- `note` - General notes (blue)
- `info` - Informational content (teal)  
- `tip` - Helpful tips (green)
- `success` - Success messages (green)
- `warning` - Warnings (yellow)
- `danger` - Critical warnings (red)
- `example` - Code examples (purple)
- `quote` - Quotes and citations (gray)