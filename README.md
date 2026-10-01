# Mate Energy: Lubricant Tank Stock Level

A web app for the warehouse team at **Mate Energy Industries Limited**. Workers type a tank dip reading and instantly get the stock in liters, with no manual chart lookup.

*Created by IIP 2026*

---

## How it works

The tank charts only list fixed values for readings ending in 0 (for example 960, 970, 980). For readings in between, the app uses linear interpolation:

```
Dip reading = 968  (between 960 = 12,500 L and 970 = 13,000 L)
((13000 - 12500) / 10) x 8 + 12500 = 12,900 Liters
```

## Confidentiality

- The chart PDFs and chart values are **never uploaded or sent anywhere**.
- They are saved only inside the browser (IndexedDB) on the computer where the manager entered them.
- Workers see the calculator only. The PDF viewer, upload, edit and delete tools appear only after **Manager login**.
- **Never commit the real chart PDFs or chart values to this GitHub repository.**

## Project structure

```
mate-tank-stock-level/
  index.html      The complete app (logo, styles and code in one file)
  manifest.json   Lets the browser install it as an app
  sw.js           Offline support
  icon-192.png    App icon
  icon-512.png    App icon (large)
  README.md    This guide
```

No installation, build step or server is needed.

## Tanks

| Group | Tanks |
|---|---|
| Main tank farms | Main Tank Farm 1, Main Tank Farm 2 |
| Horizontal tanks | Horizontal Tank 3, 4, 5, 6 |

To rename a tank, edit the text inside its `<option>` line in `index.html`. Keep the `value="Tank_1"` part unchanged, because it is the storage key.

## Deploy to GitHub Pages

1. Sign in at github.com and click **+ → New repository**.
2. Name it (for example `mate-tank-stock-level`), set it to **Public**, and click **Create repository**.
3. Click **Add file → Upload files**, drag in `index.html` (and `README.md` if you want), then **Commit changes**.
4. Go to **Settings → Pages**. Under *Build and deployment* choose **Deploy from a branch**, select `main` and `/ (root)`, then **Save**.
5. After 1 to 2 minutes the site is live at `https://YOURUSERNAME.github.io/mate-tank-stock-level/`.
6. Bookmark that link on every warehouse computer.

**Important:** do not rename the repository or change the username later. The link would change and the browser would treat it as a new site with empty storage.

To update the app later, upload a new `index.html` over the old one and commit. Saved data stays in place.

## Install as an app

Open the live link once with internet, then:
- **Windows or Mac (Chrome or Edge):** click the install icon at the right end of the address bar, then **Install**.
- **Android (Chrome):** menu (three dots) then **Install app** or **Add to Home screen**.
- **iPhone or iPad (Safari):** Share button then **Add to Home Screen**.

**Warning for iPhone and iPad:** the installed app keeps its storage separate from Safari. Set up the manager PIN, PDFs and chart values *inside the installed app*, not in Safari first.

## First-time setup (manager)

1. Open the live site and click **Manager login**. Create a PIN of at least 4 digits.
2. Select a tank. Click **Upload / Update PDF** and choose its chart PDF.
3. Enter the fixed chart values (reading and liters) for that tank and click **Save Chart Data**.
4. Repeat for all six tanks.
5. Click **Backup chart values** and keep the file somewhere safe.
6. Log out of manager mode and test: enter a reading such as 968 and check the answer against the chart.

## Daily use (workers)

1. Open the bookmarked link.
2. Select the tank.
3. Type the dip reading and press **Calculate Exact Liters** (or Enter).
4. Read the liters. The working is shown underneath so it can be checked.

If the reading is outside the chart range, the app shows a red error instead of a number. Re-check the dip.

## Data and storage: what to know

- Data persists after closing the tab or browser, and after restarting the computer.
- Each computer and each browser has its **own** storage. Set up every device the warehouse uses.
- Data is erased if someone clears browsing data for the site. Private or incognito windows keep nothing.
- **Backup chart values / Restore backup** copies the chart values between devices. PDFs are not included and must be uploaded on each device.
- The PIN only stops casual access. It is not strong security.
- **Forgot the PIN:** clear this site's data in the browser to reset it. This also erases the saved PDFs and values, so restore the chart values from the backup file and upload the PDFs again.

## Roadmap

**Version 1.0 (done)**
- Interpolation calculator with working shown
- Six tanks in two groups
- Manager PIN, PDF storage and chart value editor in the browser
- Backup and restore of chart values
- Mate Energy branding with embedded logo
- Installable app (PWA): home-screen icon, own window, works offline after the first visit

**Possible next steps**
- Daily readings log with date, time and the worker's name
- Export of readings to Excel or print to PDF
- Shared online database (such as Firebase or Supabase) so every device sees the same chart values
- Add, rename and remove tanks from the manager screen
- Low-stock and capacity warnings per tank
- Dip readings in millimeters and centimeters with unit labels

## Handover checklist

- [ ] Repository created under a company-controlled or trusted account
- [ ] GitHub Pages live and the link bookmarked on warehouse computers
- [ ] Manager PIN created and shared only with the manager
- [ ] PDFs and chart values entered for all six tanks
- [ ] Backup file saved in a safe place
- [ ] At least two people know how to restore from backup
- [ ] Test reading checked against the paper chart

---

Mate Energy Industries Limited: *Your premier source of high-quality lubricants*
