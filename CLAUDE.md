# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

Personal website for Abdul Wakeel, built with [Hugo](https://gohugo.io/) using the [hugo-coder](https://github.com/luizdepra/hugo-coder) theme. Deployed to GitHub Pages via GitHub Actions on push to `main`.

## Build & Dev Commands

- **Local dev server:** `hugo server -D` (serves at localhost:1313, `-D` includes drafts)
- **Production build:** `hugo --minify` (outputs to `./public/`)
- **New blog post:** `hugo new posts/<slug>.md`

Hugo extended version is required (the CI uses `extended: true`).

## Architecture

- `config.toml` — Site configuration (metadata, menus, theme settings, CSP policy, social links)
- `content/` — Markdown pages: `about.md`, `contact.md`, `projects.md`, `resume.md`, `posts/` (blog)
- `static/` — Static assets (images, PDF resume)
- `themes/hugo-coder` — Active theme (git submodule)
- `resources/_gen/` — Hugo's generated/compiled asset cache (CSS/SCSS)

The theme is pulled in as a git submodule. Clone with `--recurse-submodules` or run `git submodule update --init --recursive` after cloning.

## Deployment

Pushing to `main` triggers `.github/workflows/gh-pages.yml`, which builds with Hugo and deploys to the `gh-pages` branch via `peaceiris/actions-gh-pages`.
