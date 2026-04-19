# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development

This is a Jekyll-based personal site hosted on GitHub Pages. There is no local Jekyll installation — development uses Docker:

```bash
# Run dev server (http://localhost:4000)
docker run --rm --name blog -it -p 4000:4000 -v $(pwd):/srv/jekyll jekyll/jekyll /bin/bash -c "bundle install; jekyll serve --host 0.0.0.0"

# With live reload
docker run --rm --name blog -it -p 4000:4000 -v $(pwd):/srv/jekyll jekyll/jekyll /bin/bash -c "bundle install; jekyll serve --host 0.0.0.0 --livereload"
```

Build output goes to `_site/` (gitignored). GitHub Actions/Pages handles production builds automatically on push to `master`.

## Architecture

**Theme:** `pages-themes/midnight@v0.2.0` (remote theme, loaded via `_config.yml`). Custom overrides live in `css/main.css` and `_layouts/`.

**Layouts:** `_layouts/default.html` wraps all pages; `_layouts/post.html` extends it for blog posts and adds post metadata.

**Content:**
- `index.html` — home page
- `cv/index.html` — CV page
- `_posts/` — blog posts in `YYYY-MM-DD-title.md` format, published at `/blog/:year/:month/:day/:title`
- `assets/` — images, organized by post date

**Dependencies:** Managed via the `github-pages` gem (pinned in `Gemfile.lock`), which bundles a compatible Jekyll version and plugins for GitHub Pages compatibility.
