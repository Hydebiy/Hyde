# AGENTS.md

## Project Overview

Hyde is a simple **Vite + React** loan calculator app. It is a pure frontend project — no backend, no database, no external services.

## Setup

The repo was imported without scaffolding files (`package.json`, `index.html`, `vite.config.js`). These were added during Base44 setup:

- `package.json` — Vite 6 + React 18, `npm run dev` starts the dev server on port 5173
- `vite.config.js` — `@vitejs/plugin-react`, binds `0.0.0.0:5173`, `allowedHosts: true`
- `index.html` — Vite entry HTML with `<div id="root">` and `src/main.jsx`
- `docker-compose.base44.yml` — runs `node:22` with the source bind-mounted, `npm install && npm run dev`, port 3000 → 5173

## Running

```bash
docker compose -f docker-compose.base44.yml up -d --build
```

The app is served on host port 3000 (mapped to container port 5173).

## Key Files

- `src/main.jsx` — React entry point
- `src/App.jsx` — Main app component (renders `LoanC`)
- `src/LoanC.jsx` — Currently empty (the loan calculator logic lives in `App.jsx`)
- `src/LoanC.css` — Calculator styling
- `src/index.css` — Global styles
- `src/App.css` — App-level styles

## Notes

- No secrets or external credentials are required.
- The `LoanC` component is defined inline in `App.jsx`; `src/LoanC.jsx` is empty.
- No tests are configured despite the GitHub Actions workflow referencing `npm test`.
