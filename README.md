# beleg.

**Is the TV still under warranty, and where is the receipt?**

beleg. is a receipt and warranty tracker for your phone. You photograph the receipt, fill in a few fields, and beleg. shows every deadline for returns, statutory warranty and manufacturer guarantee, reminds you in time and helps you write the complaint. It is an offline PWA based on German consumer law. No AI, no server, no account.

![License: AGPL-3.0](https://img.shields.io/badge/license-AGPL--3.0-blue) ![PWA](https://img.shields.io/badge/PWA-installable-5a0fc8) ![Offline](https://img.shields.io/badge/offline-yes-2ea44f) ![No build step](https://img.shields.io/badge/build_step-none-lightgrey)

**Try it:** https://beleg.gedachtgemacht.app (works in any phone browser, install via "Add to Home Screen")

The app interface is in German.

<p align="center">
  <img src="bilder/1-uebersicht.png" width="240" alt="Overview: total value of purchases still covered, number of receipts, deadlines expiring in the next 60 days">
  <img src="bilder/2-belege.png" width="240" alt="All receipts: search, filters by category and status, receipts grouped by year with price and protection status">
  <img src="bilder/3-detail.png" width="240" alt="Receipt detail: photo of the receipt and a timeline for return, reversal of the burden of proof and statutory warranty">
</p>

## Why

The TV breaks after 20 months. The receipt is gone, or the thermal paper has faded, and nobody knows if the warranty still applies. beleg. keeps the receipt as a photo and works out the deadlines for you.

## Features

- **Capture a receipt:** photograph it with the camera (several pages), pick it from the gallery or attach a PDF invoice from an online shop. Photos are scaled down on the device.
- **Contrast for thermal paper:** optional grayscale with background correction and contrast stretching, so faded receipts stay readable. Plain image math, no ML.
- **Fields:** product, shop, purchase date, price, category, statutory warranty (24 or 12 months or none), manufacturer guarantee, return period, serial number, note. Suggestions from your earlier entries.
- **Deadlines:** return, reversal of the burden of proof, statutory warranty and guarantee for every receipt, with timeline and status.
- **Overview:** what expires in the next 60 days, how many purchases are still covered and what they are worth together.
- **All receipts:** search in product, shop, serial number and note, filter by category and status.
- **Prepare a complaint:** a factual notice of defect to the shop, asking for subsequent performance under § 439 BGB with a 14-day deadline, and a note on the reversal of the burden of proof when it applies. Copy it, send it by email or share it.
- **Share a receipt:** photos and PDF through the phone's share menu.
- **Reminders:** all upcoming deadline ends as a calendar file (.ics) with alarms 14 days and 1 day before at 9 am. Export again after changes.
- **Export:** list as CSV for German Excel, a JSON backup including all photos and PDFs, restore on another device.
- **Light and dark theme**, German number and date format, sample data to try it out.

## How beleg. calculates

| Deadline | Calculation |
|---|---|
| Return | purchase date + the days you entered |
| Reversal of the burden of proof (Beweislastumkehr) | purchase date + 12 months (purchases from 1 Jan 2022), before that 6 months, at most until the end of the statutory warranty |
| Statutory warranty (Gewährleistung) | purchase date + warranty months (24 by law) |
| Guarantee (Garantie) | purchase date + guarantee months |

Months are counted like on a calendar: 31 January plus one month is 28 February (29 February in a leap year). A deadline runs up to and including the end date. Legally the statutory warranty starts on delivery; beleg. uses the purchase date as an approximation.

## Privacy

Everything stays on your device. beleg. stores receipts, photos and PDFs in your browser's IndexedDB and makes no network requests: no analytics, no fonts or scripts from other servers, no accounts. Back up your data regularly via **Mehr · Sicherung exportieren** ("More · Export backup"), because if you clear your browser data, the receipts are gone too. On the first save, beleg. asks the browser for persistent storage.

## Install

1. Put the `beleg/` folder on any static web host (for example GitHub Pages, Netlify, your own server). HTTPS is required for the app to work offline.
2. Open the address in your phone browser.
3. In the browser menu choose **Add to Home Screen** (iPhone: Share · Add to Home Screen).

After that beleg. starts like a normal app, also without internet.

Test locally:

```sh
cd beleg
python3 -m http.server 8000
```

Then open `http://localhost:8000`.

## Legal

beleg. gives general information on German sales law (§§ 438, 439, 477 BGB) and generates a text template. This is **not legal advice**. Check deadlines and texts in each case; if there is a dispute, the consumer advice centres (Verbraucherzentralen) can help. The terms of a manufacturer guarantee are set by the manufacturer.

## License

GNU Affero General Public License v3.0 (AGPL-3.0), see `LICENSE`.

**Deutsch:** beleg. ist eine Kassenbon-App, die Belege offline speichert und Fristen für Gewährleistung, Garantie und Rückgabe berechnet, mit Erinnerung und Vorlage für die Reklamation, ohne Konto, alles bleibt auf dem Handy.

---

**gedacht.gemacht.** Small, honest software. Everything stays on your device. · [More projects](https://github.com/gedachtgemacht)
