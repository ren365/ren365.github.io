# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an academic personal website for Zehao Wang (Ph.D. candidate @ Duke University) built with Jekyll and the AcademicPages template (forked from Minimal Mistakes theme). The site is automatically deployed via GitHub Pages at https://ren365.github.io.

## Build Commands

```bash
# Install Ruby dependencies
bundle install

# Start local development server with live reload (localhost:4000)
bundle exec jekyll liveserve

# Build for production
bundle exec jekyll build

# Minify JavaScript (requires npm install first)
npm run build:js
```

**Note**: After editing `_config.yml`, you must restart the Jekyll server for changes to take effect.

## Architecture

### Content Collections
Jekyll collections organize different content types, each in their own directory:
- `_publications/` - Academic papers
- `_talks/` - Presentations and conferences
- `_teaching/` - Teaching experience
- `_portfolio/` - Project showcases
- `_posts/` - Blog posts (date-named: `YYYY-MM-DD-title.md`)
- `_pages/` - Main site pages (about, publications, research, etc.)

Each content file uses YAML front matter for metadata (layout, title, date, permalink, etc.).

### Layout Hierarchy
`compress.html` → `default.html` → `single.html` / `talk.html` / `archive.html`

### Key Directories
- `_includes/` - Reusable template fragments (author-profile, navigation, footer)
- `_layouts/` - Page layout templates
- `_sass/` - SCSS stylesheets (modular: `_variables.scss` for colors/typography)
- `_data/` - Site data files (`navigation.yml` for menu structure)
- `assets/` - Compiled CSS, JS, and fonts
- `images/` - Site images and profile photos
- `files/` - Downloadable files (PDFs, documents)

### Content Generation Tools
The `markdown_generator/` directory contains Python scripts and Jupyter notebooks to convert TSV data into markdown files:
- `publications.tsv` → individual publication markdown files
- `talks.tsv` → individual talk markdown files
- `PubsFromBib.ipynb` - Import from BibTeX

## Configuration

Main configuration is in `_config.yml`:
- Site metadata and author info
- Collection definitions and default layouts
- Markdown processing (Kramdown with GFM)
- Jekyll plugins (paginate, sitemap, gist, feed, redirect_from)

Development overrides are in `_config.dev.yml` (disables analytics, uses localhost URL).

## Navigation

Edit `_data/navigation.yml` to modify the main site menu.
