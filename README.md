# Dazztronic Blog

A modern, static blog site built with [Zola](https://www.getzola.org/) static site generator, focused on analyzed content. The site uses the DeepThought theme with extensive customizations and is deployed to GitHub Pages.

## Overview

This blog site serves as a platform for sharing PHP and Symfony development insights, tutorials, and best practices. It features a corporate design with custom styling, taxonomy-based content organization, and modern development workflows.

**Live Site**: https://dazztronic.github.io

## Architecture

### Zola vs Other Static Site Generators

If you're coming from other static site generators or Twig templating, here are key differences:

- **Template Engine**: Zola uses [Tera](https://tera.netlify.app/) templating (similar to Jinja2/Twig)
- **Content Format**: Markdown with TOML frontmatter (not YAML)
- **Build Speed**: Extremely fast builds thanks to Rust implementation
- **Asset Pipeline**: Built-in Sass compilation, no external build tools needed
- **Taxonomies**: First-class support for categories, tags, and custom taxonomies

### Template System Structure

The template system follows a hierarchical structure similar to Twig's extends/blocks:

```
templates/
├── base.html                # Main layout (like base.html.twig)
├── index.html               # Homepage
├── blog.html                # Blog listing page
├── blog-page.html           # Individual blog post
├── page.html                # Generic pages
├── macros.html              # Reusable template macros
├── taxonomy_single.html     # Generic taxonomy listing
├── categories/
│   └── single.html          # Category-specific pages
├── tags/
│   └── single.html          # Tag-specific pages
└── shortcodes/              # Content shortcodes
    ├── info.html
    ├── warning.html
    ├── tip.html
    └── ... (8 admonition types)
```

#### Template Inheritance (Like Twig extends/blocks)

```html
<!-- base.html - Main layout -->
{% block title %}{{ config.title }}{% endblock title %}
{% block content %}{% endblock %}

<!-- blog-page.html - Extends base -->
{% extends "base.html" %}
{% block title %}{{ page.title }} - {{ config.title }}{% endblock title %}
{% block content %}
  <!-- Page-specific content -->
{% endblock content %}
```

#### Recent Template Organization Improvements

The site recently underwent template reorganization for better maintainability:

1. **Generic Taxonomy Template**: Maintained `/templates/taxonomy_single.html` for categories and tags
2. **Consistent Styling**: All taxonomy pages now use the same card-based layout with corporate branding
3. **Better Content Organization**: Clear separation between different taxonomy types

## Content Structure

### Directory Organization

```
content/
├── _index.md               # Homepage content
├── blog/                     # Blog posts
│   ├── _index.md             # Blog section index
│   └── YYYY-MM/              # Date-based organization
│       └── YYYY-MM-title.md  # Post content
└── pages/                   # Static pages
    ├── impressum.md        # Legal notice
    ├── datenschutz.md      # Privacy policy
    └── ui.md               # Style guide/UI demo
```

### Content Frontmatter Format

#### Blog Posts

```toml
+++
title = "Descriptive Post Title"
date = 2025-01-20
draft = false

[taxonomies]
categories = ["AI"] 
tags = ["claude", "bash"]

[extra]
hero_image = "hero.jpg"
excerpt = "Brief description for listings and SEO"
+++

Your markdown content here...
```

### Taxonomies System

The site uses three main taxonomies:

- **Categories**: Broad content classification (`/categories/category-name/`)
- **Tags**: Specific technical topics (`/tags/tag-name/`)

All taxonomies automatically generate:
- Individual taxonomy pages
- RSS/Atom feeds
- Archive listings with card-based layouts

## Development Workflow

### Prerequisites

- **Zola 0.14.1+** - [Install Zola](https://www.getzola.org/documentation/getting-started/installation/)
- **Git** for version control
