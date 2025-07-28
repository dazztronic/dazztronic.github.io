# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **Zola-based static site blog** focused on PHP and Symfony development content. The site uses the "DeepThought" theme and is configured for deployment to GitHub Pages at `https://dazztronic.github.io`.

## Essential Commands

### Development
- `zola serve` - Start development server at localhost:1111
- `zola build` - Build the static site to `public/` directory
- `zola check` - Validate content and links

### Content Management
- `zola serve --drafts` - Include draft posts in development
- `zola build --drafts` - Build including draft content

## Site Architecture

### Content Structure
- `/content/` - All site content in Markdown format
  - `_index.md` - Homepage content
  - `blog/` - Blog posts with date-based organization (YYYY-MM-title format)
  - `pages/` - Static pages (Impressum, Datenschutz)

### Content Frontmatter Format
Blog posts use this frontmatter structure:
```toml
+++
title = "Post Title"
date = 2025-01-20
draft = false

[taxonomies]
categories = ["PHP", "Symfony"]
tags = ["specific", "tags"]

[extra]
excerpt = "Brief description for listings"
+++
```

### Template System
- `/templates/` - Custom template overrides for DeepThought theme
  - `base.html` - Main layout with corporate styling and cookie banner
  - `blog.html`, `blog-page.html` - Blog listing and individual post templates

### Theme and Styling
- Uses DeepThought theme located in `/themes/deepthought/`
- Corporate color scheme defined in `templates/base.html`:
  - Purple: `#B8A7E6`
  - Lime: `#D4E157`
  - Dark: `#2E2E2E`
- Custom CSS in templates extends theme capabilities
- Cookie banner implementation for GDPR compliance

### Static Assets
- `/static/` - Static files (images, JS, icons)
- `/public/` - Generated output (not committed to git)
- Hero images for blog posts stored alongside content

## Configuration

Main configuration in `config.toml`:
- Base URL: `https://dazztronic.github.io`
- Theme: `deepthought`
- Features enabled: Sass compilation, search index, RSS feeds
- Taxonomies: categories, tags
- GDPR: Cookie banner enabled with German text

## Content Guidelines

### Blog Posts
- Organize by date: `YYYY-MM-descriptive-title/`
- Use english language for content
- Include proper taxonomies (categories, tags)

## Deployment

Site is configured for GitHub Pages deployment:
- Built files go to `public/` directory
- GitHub Actions likely handles automated deployment
- Base URL configured for `dazztronic.github.io`

## Reading Time Calculation

Zola automatically calculates `reading_time` for all pages using a built-in algorithm:

- **Algorithm**: Based on Medium's reading time calculation (https://help.medium.com/hc/en-us/articles/214991667-Read-time)
- **Formula**: Total word count ÷ words per minute (WPM) rate
- **WPM Rate**: Approximately 265-275 WPM (Medium's standard for average adult reading speed) 
- **Word Counting**: Counts words by splitting text on whitespace (naive approach)
- **Rounding**: Result is rounded up to nearest whole minute to avoid underestimation
- **Language Limitation**: Does not work accurately for languages without whitespace
- **Template Usage**: Available in templates as `{{ page.reading_time }}` (displays as integer minutes)

The reading time appears throughout the site in:
- Blog post listings (`templates/blog.html`)
- Individual blog posts (`templates/blog-page.html`) 
- Category taxonomy pages (`templates/categories/single.html`)
- Author taxonomy pages (`templates/authors/single.html`)
- Team member article listings (`templates/taxonomy_single.html`)
- Homepage recent posts (`templates/index.html`)

## Development Notes

- Zola version 0.14.1+ required (as per theme documentation)
- Search functionality uses Elasticlunr.js
- RSS feeds generated automatically for main content and taxonomies
- Multilingual support available but currently using single language
- No build scripts or package.json - pure Zola static site generator

## Translation Policies

- Alle artikel müssen IMMER auf Englisch sein