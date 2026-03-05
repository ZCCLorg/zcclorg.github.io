# ZCCL Website Development Guide

## Quick Start

1. **Install Dependencies**
   ```bash
   bundle install --path vendor/bundle
   ```

2. **Start Development Server**
   ```bash
   bundle exec jekyll serve --host 0.0.0.0 --port 4000
   ```

3. **View Site**
   Open http://localhost:4000 in your browser

## Detailed Setup

### Prerequisites
- Ruby 2.6+
- Bundler gem

### Installation
The project uses a simplified Gemfile for better compatibility across different systems:

```bash
# Install gems locally to avoid permission issues
bundle install --path vendor/bundle
```

This installs all dependencies in the `vendor/bundle` directory, which:
- Avoids system-wide gem conflicts
- Prevents permission errors on macOS/Linux
- Is automatically excluded from Jekyll processing

### Build Commands

```bash
# Build static site (outputs to _site/)
bundle exec jekyll build

# Serve with live reload (recommended for development)
bundle exec jekyll serve --host 0.0.0.0 --port 4000

# Serve with incremental builds (faster rebuilds)
bundle exec jekyll serve --host 0.0.0.0 --port 4000 --incremental
```

### Dependencies

Current simplified Gemfile includes:
- `jekyll ~> 3.9` - Static site generator
- `kramdown-parser-gfm` - GitHub Flavored Markdown support
- `jekyll-feed` - RSS/Atom feed generation
- `jekyll-seo-tag` - SEO meta tags
- `jekyll-sitemap` - XML sitemap generation

### Troubleshooting

**Native gem compilation issues (ffi, sassc):**
- The simplified Gemfile avoids problematic native gems
- Uses Jekyll 3.x with ruby-sass instead of sassc
- Falls back to basic functionality if needed

**Permission errors:**
- Always use `--path vendor/bundle` flag
- Never run with `sudo`

**Port conflicts:**
- Change port: `--port 4001`
- Check what's using port: `lsof -i :4000`

### Project Structure

```
├── _config.yml          # Jekyll configuration
├── _data/               # Data files (YAML)
├── _includes/           # Reusable template parts
├── _layouts/            # Page layouts
├── _sass/               # Sass stylesheets
├── css/                 # Compiled CSS
├── images/              # Site images
├── vendor/              # Local gem installation (excluded)
├── Gemfile              # Ruby dependencies
└── *.html               # Site pages
```

### Content Updates

- **Homepage**: Edit `index.html`
- **Pages**: Edit individual `.html` files
- **Site config**: Edit `_config.yml`
- **Team info**: Edit `team.html`
- **Publications**: Edit `publications.html`

Changes are automatically reflected with live reload enabled.