# Privacy Policy — MTG Marketplace Companion

_Last updated: 2026-05-13_

This privacy policy describes what data the **MTG Marketplace Companion** Chrome extension ("the extension") collects, where it is stored, and what is (and is not) transmitted off your device.

## Plain-English summary

- The extension reads pages on a small set of trading-card marketplaces while you browse them, and saves details of orders you have made to a local database on your own computer.
- Nothing is sent to the developer of the extension. There is no backend server.
- If you choose to enable Drive sync, an encrypted-at-rest copy of your captured data is stored in **your own Google Drive** (using a scope that prevents the extension from accessing anything else in your Drive).
- You can delete all data at any time from the Settings page, or by uninstalling the extension.

## What data is captured

The extension captures the following from order-related pages you visit on supported marketplaces (TCGPlayer, Manapool, TheTCGMarketplace, Card Kingdom, Star City Games, Games Haven):

- **Purchase details**: card name, quantity, set, condition, foil status, price, currency, order date, order status.
- **Order metadata**: order ID, seller name, payment method label (e.g. "PayNow", "Visa ending in 1234" — the label only, never the full card number or CVV).
- **Shipping and billing addresses** as printed on the order confirmation page.
- **Tracking numbers** when present.
- **Cart contents** when you visit the marketplace's cart page (used to enable the cross-marketplace price comparison feature).

The extension also reads card data from [Scryfall](https://scryfall.com) (public API, no credentials) to match purchased cards to canonical printings and prices.

The extension does **not** capture:

- Passwords, security codes, full credit card numbers, or any other authentication credentials.
- Browsing activity outside the marketplace pages it is explicitly granted permission to read.
- Page content from any other website.

## Where the data is stored

All captured data is stored in your browser's local IndexedDB on your own computer, scoped to the extension's own origin. It is not shared with other browser extensions, websites, or browser profiles.

**Optional Google Drive sync** — if you enable Drive sync in Settings:

- The extension requests the `https://www.googleapis.com/auth/drive.file` OAuth scope. This scope only allows the extension to read and write files that **the extension itself created** — it cannot access any other files in your Drive.
- A single JSON file (named `MTG Marketplace Companion / history.json`) is written to your Drive containing the same captured data described above, so that other Chrome profiles where you install the extension can sync the same history.
- This file is in your own Drive. The extension developer has no access to it.

## What is transmitted off your device

When you actively use the extension, the following network requests are made on your behalf:

- **Scryfall** (`api.scryfall.com`) — card lookups for matching captured items to canonical card data. No personal information is sent; just card names, set codes, and Scryfall card UUIDs.
- **Frankfurter** (`api.frankfurter.app`) — public currency conversion rates when you enable currency conversion in Settings. No personal information is sent.
- **Google Drive API** (`googleapis.com`) — only if you have opted into Drive sync. Used to read and write the single sync file described above.
- **The marketplaces themselves** (TCGPlayer, Manapool, etc.) — when you click the extension's "Backfill" feature, the extension makes the same kinds of requests your browser would make if you clicked through their order-history pages. Marketplace requests use your existing session cookies for those sites; the extension does not transmit your credentials anywhere.

**No data is transmitted to the extension developer**, to any analytics service, or to any third party not listed above.

## Use of Google API data

In accordance with Google's [Limited Use](https://developers.google.com/terms/api-services-user-data-policy#additional_requirements_for_specific_api_scopes) requirements:

- Google user data (the single sync file on your Drive) is used **only** to provide the user-facing sync feature.
- Google user data is **not** transferred to others except as necessary to provide the feature, or when required by law.
- Google user data is **not** used for serving advertisements.
- Humans do not read this data except (a) with your explicit consent for support purposes, (b) for security purposes including investigating abuse, or (c) to comply with applicable law.

## Your control over the data

- **Delete locally**: open Settings → "Wipe all data" (irreversible).
- **Delete the Drive file**: open your Google Drive, locate `MTG Marketplace Companion / history.json`, and delete it. You can also revoke the extension's Drive access at any time via [Google Account → Security → Third-party apps](https://myaccount.google.com/permissions).
- **Uninstall**: removing the extension from `chrome://extensions` deletes the local database. The Drive file (if you have one) is **not** automatically deleted; delete it manually as above if desired.
- **Per-site capture toggles**: open Settings → Site capture to disable capture for individual marketplaces.

## Changes to this policy

If material changes are made to this policy, the version date at the top of this document will be updated, and a note will appear in the extension's Settings view describing the change.

## Contact

For privacy questions, data deletion requests, or to report a security issue, open an issue on the public repository:

<https://github.com/cheokjiade/mtg-card-marketplace-companion-public/issues>
