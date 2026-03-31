# Atomic Static Site

This repo is deployed by **Atomic**, a self-hosted tool that serves static sites from git repos.

## How deployment works

1. Atomic clones this repo into a Docker container
2. All files are served as-is by Python's `http.server` on port 8000
3. There is **no build step** — no bundler, no compiler, no npm
4. Atomic polls for new commits every 5 minutes and auto-redeploys on changes

## Constraints

- **`index.html` must exist at the repo root.** This is the entry point.
- **Static files only.** HTML, CSS, JS, images, fonts, etc. No server-side code will execute.
- **No build tools.** Everything in the repo is served directly. If you need compiled output (e.g., TypeScript, Sass), compile locally and commit the output.
- **All files in the repo are deployed.** The entire repo contents end up in the container. Don't commit secrets or large files you don't intend to serve.
- **Relative paths only.** Link between pages and assets using relative paths (e.g., `./styles.css`, `./images/logo.png`). No absolute paths starting with `/` since the site may not be served from the domain root.

## File structure

```
index.html      <- required entry point
styles.css      <- stylesheets
scripts.js      <- client-side JS (optional)
images/         <- images and other assets (optional)
pages/          <- additional HTML pages (optional)
```

## Common mistakes to avoid

- Adding a `package.json` with a build script but not committing the build output
- Using server-side features (PHP, Node, Python scripts) — they won't execute
- Referencing CDN or external URLs that may be unavailable — prefer vendoring dependencies
- Committing `.env` files, credentials, or other secrets
