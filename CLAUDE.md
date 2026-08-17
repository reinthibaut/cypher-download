# CLAUDE.md — Cypher Download

## What this project does
The **public** download page for Cypher App. It exists so Rein can share one link with
friends and family instead of sending an 80 MB file over WhatsApp.

The app's source code is NOT here — it lives in the private `Reins-Cypher` repo.
This repo holds only the install page and the released installer.

## File structure
- `docs/index.html` — the download page, served by GitHub Pages
- `README.md` — same install instructions, for anyone who lands on the repo itself

## Where things live
- Public repo: `github.com/reinthibaut/cypher-download`
- Live page: `reinthibaut.github.io/cypher-download`
- Installer: attached to the GitHub Release in this repo, named `CypherApp-Setup.exe`
- Private source: `github.com/reinthibaut/Reins-Cypher`

## Rules
- **This repo is public.** Never put keys, personal data, `.env` files, or app source here.
- The release asset must always be named `CypherApp-Setup.exe` — the download button links
  to `/releases/latest/download/CypherApp-Setup.exe`, which only resolves if the filename
  stays identical across versions. Renaming it silently breaks the download button.
- GitHub Pages serves from the `docs/` folder on `main`. Changing that folder breaks the site.
- Never run git commands without asking Rein first.
- Never delete files without confirming.

## Publishing a new version
1. Build in the private repo: `npm run dist`
2. Copy `dist/Cypher App Setup <version>.exe` and rename it to `CypherApp-Setup.exe`
3. Create a release here with that file attached
4. Update the version number shown in `docs/index.html` and `README.md`

## Stack
Static HTML, no build step, no dependencies. GitHub Pages for hosting.
