# FMM Operations v2.6 — product audit and regression report

**Scope:** clean v2.6 application code, synthetic test records only. Private backups were never included.

## Pass 1 — whole-app render
- All nine screens rendered: dashboard, quotations, budgets, archive, master programme, project Gantt, resources, cashflow and readiness.
- Desktop 1440×900 and mobile 390×844 browser visual checks; no JavaScript errors.

## Pass 2 — cross-record navigation
- Global search reaches job/quotation refs, clients, material lines, activities, cash events, readiness, resources and absences.
- Search-to-cost-line; search-to-activity; project hub to linked original quotation, costs, cashflow, readiness and Gantt; archive/budget Overview.
- `Ctrl+K`, arrows/Enter/Escape keyboard navigation, and deliberate HTML-like search text escaped correctly.
- Stress fixture: **141 synthetic projects**, roughly **6,048 indexed records**; search indexed in approximately **300 ms** in test browser (not a universal speed guarantee).

## Pass 3 — complete business lifecycle
Create quotation → itemised cost and mark-up → client print preview → accept → convert into project → schedule an activity → record cash event → linked costing → mark complete → archive → restore. Full JSON backup, clear synthetic data, import, and verify link between project and quote. Full ZIP export created **14 files** including company JSON backup.

## Pass 4 — resources, financials, readiness
- Resource overbooking detected; new subcontractor and absence saved.
- Pre-start blocker persisted; project date shift propagated; clash calculation remained valid.
- Optimised cashflow matched legacy calculation on small and stress datasets.

## Pass 5 — OneDrive and safety
- Mock Microsoft Graph verified token renewal, cloud baseline, ETag-conditional uploads, safe automatic download, conflicts and guarded master selection, HTTP 412 conflict and reconnect.
- New download race: local edits made while a remote file loaded were preserved; auto-replace stopped and newer cloud version flagged.
- Mobile Section selector exposed all nine choices; no app data mutation from reading/searching.

## Limitations
- Microsoft OAuth/Graph tests were simulated, **not** executed against the user's live OneDrive account.
- Print preview invoked; physical printers and drivers not tested.
- No real QuickBooks integration, external document permissions, or multi-user collaborative editing tested.
- Code deploy leaves company schema, cloud database and Entra registration unchanged.

Rollback: `backup/v2.5-pre-v2.6`.
