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
  - Linux: `CypherApp.AppImage` (any distro) and `CypherApp.deb` (Ubuntu/Mint/Debian)
- Private source: `github.com/reinthibaut/Reins-Cypher`

## Rules
- **This repo is public.** Never put keys, personal data, `.env` files, or app source here.
- Release assets must always be named `CypherApp-Setup.exe`, `CypherApp.dmg`,
  `CypherApp.AppImage` and `CypherApp.deb` — the download links point at
  `/releases/latest/download/<name>`, which only resolves if the filenames stay identical
  across versions. electron-builder produces versioned names like
  `Cypher App-2.0.0-universal.dmg`, so they must be renamed before uploading. Getting this
  wrong breaks the download button silently — the page still looks fine.
- The `.deb` maintainer email lives in `package.json` under `build.linux.maintainer` and is
  readable by anyone who downloads the package, so it uses the GitHub noreply address rather
  than a personal one. Building a `.deb` fails outright without it.
- GitHub Pages serves from the `docs/` folder on `main`. Changing that folder breaks the site.
- Never run git commands without asking Rein first.
- Never delete files without confirming.

## Publishing a new version
1. **Windows**: in the private repo run `npm run dist`, then rename
   `dist/Cypher App Setup <version>.exe` to `CypherApp-Setup.exe`
2. **macOS and Linux**: trigger the "Build installers" workflow in the private repo
   (`gh workflow run build-installers.yml --repo reinthibaut/Reins-Cypher`), download
   both artifacts, then rename:
   - `Cypher App-<version>-universal.dmg` → `CypherApp.dmg`
   - `Cypher App-<version>.AppImage` → `CypherApp.AppImage`
   - `cypher-app_<version>_amd64.deb` → `CypherApp.deb`

   Neither build can run on Windows — macOS packaging needs `hdiutil`, Linux needs
   `dpkg`/`fakeroot`.
3. Create a release here with all four files attached
4. Update the version number shown in `docs/index.html` and `README.md`

## Stack
Static HTML, no build step, no dependencies. GitHub Pages for hosting.
