Check that this repo is valid for deployment via Atomic. Run these checks and report the results:

1. **index.html exists** at the repo root (required entry point)
2. **No server-side code** — flag any .py, .rb, .php, .go, .rs files that appear to be server code (ignore config/tooling scripts)
3. **No unbundled build tools** — if package.json exists, check that it doesn't have a "build" script without corresponding output committed (e.g., a dist/ or build/ directory)
4. **No secrets** — flag any .env files, credentials.json, or similar
5. **No absolute paths** — scan HTML files for `href="/"` or `src="/"` patterns that won't work when served from a subdirectory
6. **Reasonable size** — flag any files over 10MB that probably shouldn't be in a static site repo

Report each check as PASS or FAIL with details.
