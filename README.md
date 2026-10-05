# Communication Theory Primer Site (Jekyll + GitHub Pages)

This repository contains a Jekyll-powered website scaffold designed for publication on GitHub Pages.

## Project structure

- `/index.md` — home page
- `/pages/` — six required subpages
- `/_layouts/` — reusable page templates
- `/assets/css/style.css` — global styles and color variables
- `/images/` — image folder for future content assets
- `/.github/workflows/jekyll.yml` — automated build/deploy workflow for pushes to `main`
- `/_config.yml` — Jekyll configuration (includes GitHub user/repository path settings)

## Local development

### 1) Install dependencies

```bash
bundle install
```

### 2) Run the site locally

```bash
bundle exec jekyll serve
```

Then open `http://127.0.0.1:4000/comm-primer/`.

### 3) Build static output

```bash
bundle exec jekyll build
```

Generated files are written to `/_site`.

## Content authoring guide

You are expected to replace and expand the boilerplate text. Use this workflow:

1. Pick the target page in `/pages/` or `index.md`.
2. Edit the front matter fields:
   - `title` — page title
   - `lead` — short introductory sentence
   - `permalink` — page URL (subpages already configured)
3. Write content in Markdown under the front matter block.
4. Add section headings (`##`, `###`) to keep pages readable.
5. For lists of concepts, prefer ordered or unordered lists.
6. When adding images:
   - Place files in `/images/`
   - Reference with root-relative paths, for example:
     ```md
     ![Descriptive alt text]({{ '/images/example-diagram.png' | relative_url }})
     ```
   - Always include meaningful alt text.

## Accessibility guidance

The scaffold already includes:

- semantic regions (`header`, `nav`, `main`, `footer`)
- ARIA labels for major landmarks
- a keyboard-accessible skip link
- high-contrast colors

When adding new content, keep accessibility strong:

- use headings in order
- avoid vague link text (avoid “click here”)
- add alt text to every informative image
- keep paragraph length moderate for readability

## Basic style customization

Open `/assets/css/style.css` and update CSS variables in the `:root` block:

- `--color-bg`
- `--color-surface`
- `--color-text`
- `--color-muted`
- `--color-primary`
- `--color-primary-strong`
- `--color-border`

These variables control most of the visual palette globally.

## GitHub Pages behavior

The GitHub Actions workflow in `/.github/workflows/jekyll.yml` automatically runs on every push to `main`, builds the Jekyll site, uploads the artifact, and deploys to GitHub Pages.

If Pages is not yet enabled for the repository, enable it in GitHub settings and choose **GitHub Actions** as the source.
