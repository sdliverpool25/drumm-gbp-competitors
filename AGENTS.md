# Base44 Dev Environment

## Project type
Static single-page website. One `index.html` with inline CSS/JS plus image assets in `assets/`. No backend, no build step, no dependencies.

## Running the preview
```bash
docker compose -f docker-compose.base44.yml up -d
```
Serves on http://localhost:3000 via nginx:alpine.

## Key details
- The repo root directory has restrictive permissions (700), so nginx must run as `user root;` — configured in `nginx.dev.conf`.
- The only JS in the page uses localStorage for checkbox persistence; no server-side state.
- Edits to `index.html` or `assets/` are immediately visible (nginx serves files fresh on each request). Call `reload_preview` after edits if the browser cache needs clearing.
- No secrets or external credentials required.
