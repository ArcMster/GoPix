# GoPix

A photo editor that runs entirely in the browser and works offline once installed.

## Files

- `index.html`: the whole app (markup, styles, script)
- `manifest.json`: install metadata (name, icons, colours, file handling)
- `sw.js`: service worker that caches the app for offline use
- `icons/`: logo and app icons
  - `icon-192.png`, `icon-512.png`: install icons (rounded tile)
  - `icon-maskable-512.png`: Android adaptive icon, logo kept inside the safe zone
  - `apple-touch-icon.png`: iOS home screen icon (180px, square, iOS rounds it)
  - `icon-64.png`, `favicon-32.png`: header logo and browser tab
  - `logo-full.png`: full logo with the GoPix wordmark, for README, store listing or social posts
  - `logo-mark.png`: camera mark only, on the brand navy

## Run it

Service workers need `https://` or `localhost`, so opening `index.html` directly from disk gives you the editor without install or offline support.

Local test:

    python3 -m http.server 8080

Then open http://localhost:8080.

Deploy: upload the folder as is to any static host (GitHub Pages, Firebase Hosting, Netlify). All paths are relative, so it works from a subfolder too.

## Shipping an update

Change `VERSION` in `sw.js` (for example `gopix-v2`) each time you deploy, so installed copies pick up the new files.
