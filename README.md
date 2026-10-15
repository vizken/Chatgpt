# Vizken Web Application Lab

A mobile-first, extensible launcher for independent HTML/Web3D experiments. **Existing application URLs must remain unchanged.**

## Current applications
- APP-001 Annotation — `/index.html` (Three.js world-space dimensions)
- APP-002 Anime-chair — `/anime-chair.html` (exploded chair animation)
- APP-003 Apartment12 — `/apartment12/` (architectural model)

## Publishing rules
1. Every new application receives a permanent unique APP ID and an independent entry point under `apps/appNNN/index.html`. Existing legacy applications stay at their current URLs.
2. Register each application in `config/apps.json`. The Lab reads this registry at runtime; never hardcode a fixed number of applications.
3. Keep HTML/CSS/JS/assets within the application directory. Do not modify unrelated applications.
4. For updates, reuse the existing APP ID and path; preserve Git history and increment the version.
5. Test direct loading, asset paths, mobile layout, and Lab launch links before claiming deployment succeeded.
6. The GitHub Pages site is hosted under `/Chatgpt/`: use URL resolution relative to the Lab page and do not assume a domain-root deployment.
7. Never commit credentials, API tokens, or private data to this public repository.
8. Publishing from ChatGPT requires an authorized GitHub write operation; successful commit does not by itself prove Pages deployment.
9. Keep the launcher at `/lab/` and preserve the root `index.html` annotation application.
10. Update `docs/CHANGELOG.md` after changes. Avoid destructive restructuring without approval.

## Mobile workflow
Create HTML in ChatGPT → request “上傳 Lab” → validate → commit to GitHub → update registry → verify GitHub Pages → return direct application URL.

## Registry
`config/apps.json` contains `schemaVersion` and an `applications` array. Each entry requires `id`, `name`, `description`, `category`, `path`, `status`, `version`. Paths are resolved relative to `/lab/`.

## Development
Serve locally using `python -m http.server 8000`, then open `/lab/`. File protocol loading is not supported for JSON fetch.

## Agent policy
See [AGENTS.md](AGENTS.md).
