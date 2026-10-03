# Mate Energy: Lubricant Tank Stock Level

Warehouse tool for Mate Energy Industries Limited. Select a tank, type the dip reading (mm) and get the exact liters. Readings between chart steps are worked out by linear interpolation, with the working shown.

## Files

```
mate-tank-stock-level/
  index.html      The complete app (logo, charts for Tanks 1 to 6 and code in one file)
  manifest.json   Lets the browser install it as an app
  sw.js           Offline support
  icon-192.png    App icon
  icon-512.png    App icon (large)
  README.md       This guide
```

## Deploy to GitHub Pages

1. On github.com click **+ then New repository**. Name it `mate-tank-stock-level` and click **Create repository**.
2. Click **Add file then Upload files**, drag in `index.html`, `manifest.json`, `sw.js`, `icon-192.png`, `icon-512.png` (and `README.md`), then **Commit changes**.
3. Open **Settings then Pages**. Under *Build and deployment* choose **Deploy from a branch**, select `main` and `/ (root)`, then **Save**.
4. After 1 to 2 minutes the app is live at `https://YOURUSERNAME.github.io/mate-tank-stock-level/`.

The file must be named `index.html` and sit at the top level of the repository.

## Install as an app

Open the live link once with internet, then:
- **Windows or Mac (Chrome or Edge):** click the install icon at the right end of the address bar, then **Install**.
- **Android (Chrome):** menu (three dots), then **Install app**.
- **iPhone or iPad (Safari):** Share, then **Add to Home Screen**. The installed app keeps its own storage, so set the PIN and restore backups inside it.

It also works offline after the first visit. A restored backup is now saved in the browser (IndexedDB) and is still there after closing the app.

## Manager tools

- Default PIN is **1234**. Click **Change PIN** straight away and choose a new one.
- **Backup chart values** saves the chart data to a file. **Restore backup** loads it back.
- The PIN is stored in the browser, and each device keeps its own PIN.

## Important: confidentiality

The chart values for all six tanks are written inside `index.html`. On a public GitHub repository, anyone who opens the page source can read them. Decide with the company whether that is acceptable before publishing. If not, use a private repository (GitHub Pages on private repositories needs a paid GitHub plan) or host the file on an internal computer instead.

