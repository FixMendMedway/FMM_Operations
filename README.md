# FMM Operations v2.8 — Business Overview

[Open the live application](https://fixmendmedway.github.io/FMM_Operations/)

v2.8 is a clarity-first interface overhaul of FMM Operations v2.7. It keeps the Fix & Mend Medway slate/lime theme, existing records, quotation and costing formulas, mileage logs, programme, archives and Microsoft OneDrive sync unchanged.

## What changed

- **One business dashboard:** current projects, leads/unconverted quotations, issues needing attention and business mileage. All headline figures open their underlying records.
- **Click-through home:** projects, dates, status, upcoming tasks, warnings and recent entries have full-row drill-down, not tiny links.
- **Project detail drawer:** overview, budget & itemised cost lines, programme, site/job records, mileage. Open the original editing form or specialist module when needed. Reading details does not edit data.
- **Simpler navigation:** main work areas are visible; planning and history are grouped. Click the logo to return home. Global search retains Ctrl+K. Export, backup, import, print and New quote are grouped under **Tools**.
- **Responsive layouts:** desktop and mobile, with the existing mobile section selector retained.

All 11 existing modules remain accessible. This release adds **no new data fields, accounting integrations, invoicing, payment processing or financial documents**.

## Safe upgrade

1. In v2.7 select **Backup all** and save the private JSON outside GitHub.
2. Check that the newest browser data has been saved to OneDrive; do not edit in two browsers concurrently.
3. After a successful GitHub Pages deployment, refresh https://fixmendmedway.github.io/FMM_Operations/ and confirm **FMM OPERATIONS · V2.8** in the sidebar.
4. Open the dashboard metrics, project detail tabs and mileage entry. Confirm job names, quotations and costs match v2.7.
5. Test one controlled edit, Save to OneDrive, then Load from OneDrive in a second v2.8 browser. Take a fresh dated JSON backup.

## Important limits

- Company data remains in private OneDrive app-folder JSON and browser storage; GitHub stores **public code only**.
- No database schema migration. App deploy does not alter OneDrive company data.
- OneDrive is still a single-writer snapshot sync using conditional ETags, not real-time collaborative editing. Keep dated backups.
- Automated interface tests used synthetic records and stubbed browser storage. Real Microsoft sign-in, two-browser sync and physical printing remain final user acceptance checks.
- Older app available at `backup/v2.7-before-v2.8`. Rolling back code does not roll back data.
