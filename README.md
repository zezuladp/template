# Atomic Static Site Template

A starter template for static sites deployed with [Atomic](https://github.com/dzezula/atomic).

## Getting started

1. Clone or use this template to create a new repo
2. Edit `index.html` and `styles.css`
3. Push — Atomic will pick up changes automatically

## Local preview

```sh
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Rules

- `index.html` at the repo root is required
- Static files only (HTML, CSS, JS, images) — no server-side code
- No build step — everything is served as-is
- Don't commit secrets or `.env` files

## Git hooks

To enable the pre-commit validation hook:

```sh
git config core.hooksPath .githooks
```

## Claude Code

This repo includes Claude Code configuration:

- `/validate` — check the repo meets Atomic's requirements
- `/preview` — start a local preview server
