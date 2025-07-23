# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a Hugo-based personal website and blog for Tobias Mende, built using the `lightbi-hugo` theme. The site contains blog posts, talks, and personal information, focusing on software engineering leadership, developer experience, and organizational development topics.

## Common Commands

- **Build site**: `hugo` (run from `src/` directory)
- **Development server**: `hugo server -D` (run from `src/` directory)
- **Build for production**: `hugo --minify` (run from `src/` directory)

## Architecture & Structure

### Key Directories
- `src/` - Main Hugo site source code
  - `src/content/blog/` - Blog posts in Markdown format
  - `src/content/talks/` - Talk information and slides
  - `src/assets/` - SCSS styles and images
  - `src/layouts/` - Custom Hugo templates
  - `src/static/` - Static assets (favicon, PDFs, etc.)
  - `src/hugo.toml` - Hugo configuration file
- `src/public/` - Generated static site (build output)
- `src/themes/lightbi-hugo/` - Hugo theme

### Content Creation
- Blog posts follow naming convention: `YYYY-MM-DD-title-slug.md`
- Blog archetype at `src/archetypes/blog.md` generates frontmatter automatically
- Images for blog posts go in `src/assets/img/blog/` and `src/static/img/`
- Talk slides are stored in `src/static/slides/`

### Configuration
- Main config: `src/hugo.toml`
- Site uses Disqus for comments
- Matomo analytics integration
- Lunr search enabled
- Social media links configured in author section

### Content Structure
- Author information and social links defined in `hugo.toml`
- Menu structure defined in config file
- Blog posts use Hugo's frontmatter with title, slug, image, date, description, and tags
- Publication dates control when content appears

## Development Notes

- Site is deployed to production at `https://mende.io`
- No package.json - pure Hugo static site generator
- Uses SCSS for styling (compiled by Hugo)
- Theme customizations in `src/layouts/`
- No build tools beyond Hugo required