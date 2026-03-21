# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll-based resume website using the online-cv theme, deployed to GitHub Pages. The site is a single-page resume with a sidebar layout.

## Architecture

**Data-driven approach**: All resume content (experience, education, skills, projects) is defined in a single YAML file at `docs/_data/data.yml`. This is the single source of truth - the Jekyll templates pull from this file to render the site.

**Working directory**: Jekyll runs from `./docs`, not the repository root. All Jekyll/bundle commands must be executed from this directory.

**Deployment**: GitHub Actions automatically builds and deploys to GitHub Pages on push to main. The workflow is at `.github/workflows/jekyll.yml` and handles Ruby setup, Jekyll build, and deployment.

## Common Commands

### Local Development
```bash
# Install dependencies (run from docs/)
cd docs && bundle install

# Run development server (run from docs/)
cd docs && bundle exec jekyll serve
# Site will be at http://localhost:4000/profile/
```

### Content Updates
All content changes should be made in `docs/_data/data.yml`:
- Personal info and sidebar links (email, LinkedIn, GitHub, etc.)
- Career profile summary
- Work experiences
- Education
- Skills and proficiency levels
- Projects
- Languages and interests

### Configuration
- `docs/_config.yml`: Site settings (title, URL, baseurl, plugins)
- The `baseurl` must match the GitHub repository name for proper deployment

### PDF Resume
Place PDF files in `pdf/` and reference them in `docs/_data/data.yml` under `sidebar.pdf`

## Key Files
- `docs/_data/data.yml`: All resume content
- `docs/_config.yml`: Jekyll configuration
- `docs/_layouts/default.html`: Main page layout
- `docs/_includes/sidebar.html`: Sidebar template
- `docs/index.html`: Homepage that renders the resume
