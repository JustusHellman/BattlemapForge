# Battlemap Forge

A browser tool for painting D&D battle maps. Everything is in `index.html`; there is nothing to install or build.

## Run it on your own PC

Double-click `index.html`. It opens in your browser and works offline. Your current map and saved stamps are kept in that browser automatically.

## Put it online with GitHub Pages

1. Create a new repository on GitHub (for example `battlemap-forge`). It can be public or private, but free accounts need it public for Pages.
2. Upload everything in this folder, including the hidden `.github` folder and `.nojekyll`. The easiest way is **Add file → Upload files** and dragging the whole folder in, or with git:
   ```
   git init
   git add .
   git commit -m "Battlemap Forge"
   git branch -M main
   git remote add origin https://github.com/YOUR-NAME/battlemap-forge.git
   git push -u origin main
   ```
3. In the repository, go to **Settings → Pages**, and under **Build and deployment** set **Source** to **GitHub Actions**.
4. Open the **Actions** tab and wait for "Deploy to GitHub Pages" to finish (about a minute). Your site is at `https://YOUR-NAME.github.io/battlemap-forge/`.

To update the tool later, replace `index.html` and push (or upload) again; the site redeploys on its own.

## Moving maps between copies

Each copy (the one in Claude, a double-clicked file, the GitHub Pages site) keeps its own autosave and stamps. Use **Export → Save map file** in one and **Open map file** in another to move a map.

## VTT export

**Export → Export for VTT** writes a Universal VTT file (`.dd2vtt`) with the map image plus walls, doors and lights. In Foundry VTT, import it with the *Universal Battlemap Importer* module.

**Image format:** PNG works everywhere; **WebP** makes the same map about ten times smaller (a 30 × 22 map at 100 px per square: ~15 MB as PNG, ~1 MB as WebP). Most VTTs read WebP; if one doesn't, export PNG. (Safari can't write WebP, so it always gives PNG.)

## Inside DnDocs

DnDocs opens this same page full screen (`?embed=dndocs`) from a battle map's settings: **Make a map in Battlemap Forge** or **Edit this map in Battlemap Forge**. In that mode there's a **Send to DnDocs** button that puts the map (grid, walls, doors) straight onto the battle map, together with the editable map file so it can be reopened and changed later.

- There is only this one copy of the code: DnDocs loads it from the GitHub Pages site, so any change pushed here shows up in DnDocs straight away.
- Maps made from DnDocs autosave in their own slot, so they never replace the map you're working on here.
- The page only talks to the DnDocs page that opened it (same site, or a local development copy on `localhost`).
