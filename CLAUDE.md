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
- Installers: attached to the GitHub Release in this repo
  - Windows: `CypherApp-Setup.exe`
  - macOS: `CypherApp.dmg` (universal — runs on both Apple Silicon and Intel)
- Private source: `github.com/reinthibaut/Reins-Cypher`

## Rules
- **This repo is public.** Never put keys, personal data, `.env` files, or app source here.
- Release assets must always be named `CypherApp-Setup.exe` and `CypherApp.dmg` — the
  download buttons link to `/releases/latest/download/<name>`, which only resolves if the
  filenames stay identical across versions. electron-builder produces versioned names like
  `Cypher App-1.1.0-universal.dmg`, so they must be renamed before uploading. Getting this
  wrong breaks the download button silently — the page still looks fine.
- GitHub Pages serves from the `docs/` folder on `main`. Changing that folder breaks the site.
- Never run git commands without asking Rein first.
- Never delete files without confirming.

## Publishing a new version
1. **Windows**: in the private repo run `npm run dist`, then rename
   `dist/Cypher App Setup <version>.exe` to `CypherApp-Setup.exe`
2. **macOS**: trigger the "Build macOS" workflow in the private repo
   (`gh workflow run build-mac.yml --repo reinthibaut/Reins-Cypher`), download the
   artifact, then rename `Cypher App-<version>-universal.dmg` to `CypherApp.dmg`.
   The Mac build cannot run on Windows — it needs a GitHub-hosted Mac.
3. Create a release here with both files attached
4. Update the version number shown in `docs/index.html` and `README.md`

## Stack
Static HTML, no build step, no dependencies. GitHub Pages for hosting.
