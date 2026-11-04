# FMM Operations v2.4

A browser-based, local-first operations application for Fix & Mend Medway: quotations, editable Groups, labour and material budgets, converting quotes into projects, Gantt planning, resources, cashflow, readiness and a retrievable archive.

## Security

**This repository contains application code only.** Do not upload business JSON backups, client data, exported spreadsheets, documents, tokens or Microsoft client secrets. Your live data belongs in your private OneDrive account using the in-app OneDrive sync.

## Hosting on GitHub Pages

1. In repository **Settings → Pages**, set **Deploy from a branch**, **main**, **/(root)**.
2. When GitHub Pages provides your HTTPS website address, use that exact address in your Microsoft Entra single-page application (SPA) registration as the redirect URI.
3. A free GitHub plan generally needs the repository to be **public** to use GitHub Pages. This repository is currently private. If you want free Pages hosting, change its visibility only after confirming the code contains no private data; never publish your JSON backups.

## Microsoft OneDrive cloud sync

1. Create an app registration at https://entra.microsoft.com, allowing the Microsoft account type you actually use for OneDrive.
2. Add the **Single-page application** platform and the exact GitHub Pages URL as the redirect URI.
3. Add delegated **Microsoft Graph Files.ReadWrite.AppFolder** permissions; do **not** create or embed a client secret.
4. Copy the public Application (client) ID to **OneDrive sync** in FMM Operations and sign in.
5. Export a local JSON backup before the first cloud save. Load your existing jobs from a private backup, **Save to OneDrive**, then use **Load from OneDrive** on any other signed-in device.

The browser stores a local draft. Cross-device sharing uses a single private OneDrive JSON snapshot, not simultaneous multi-user collaboration. If the cloud version changes elsewhere, the app prevents overwriting it until you resolve the conflict. Save regular backups.

## Features and exports

- Live itemised pricing with editable Group names, cost rates, markups, labour/material splits and stock-material tracking.
- Quotation to active project conversion, linked project Gantt phases and a searchable completed-project archive.
- Internal cost report and client quotation print/PDF layouts; client copies omit internal costs and profit.
- Full JSON and ZIP exports, CSV quotation cost lines, and project/Gantt print views.

## Testing and limitations

Automated browser checks covered navigation, a nine-project backup import, quote conversion, Group editing, stock accounting, archives, and exports. Print tests covered multi-page client/internal quotations and a Gantt report. Microsoft Graph integration was tested with a mock; **a real Microsoft sign-in and save/load must still be verified** after Azure registration.

Released 4 November 2026. Use one editing device at a time until a multi-user backend exists.
