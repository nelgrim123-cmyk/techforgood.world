# techforgood.world

Jekyll site for techforgood.world — notes on technology applied to healthcare.
Author: Nello Grimaldi.

## Structure

- `index.md` — home (layout: home)
- `about.md` — about page (layout: page)
- `digital-point-of-care.md`, `tech-in-pharma.md`, `ai-powered-rd.md` — the three pillar pages (layout: pillar); the markdown body is the "Why it matters" section
- `_posts/` — articles; each post needs `title`, `categories` (one of the three pillar slugs) and `read_time`
- `_layouts/` — default, home, pillar, post, page
- `_includes/` — header, footer
- `assets/css/main.css` — all styling
- `assets/images/` — logo mark, favicon, profile photo

## Adding an article

Create `_posts/YYYY-MM-DD-slug.md`:

```
---
title: "Your title"
categories: [tech-in-pharma]
read_time: 5
---

Body in markdown. Use `## Heading` for sections.
```

It appears automatically on its pillar page.

## Local preview

```
bundle install
bundle exec jekyll serve
```
