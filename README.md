# FMM Operations v2.6

**Fix & Mend Medway** — browser-based, local-first quotation, job budgeting, scheduling, resources, cashflow and project archive software.

App: https://fixmendmedway.github.io/FMM_Operations/

## What's new in v2.6

- **Find anything**: universal local-only search across projects, clients, references, quotations, Groups, individual cost lines, activities, Gantt phases, cash events, pre-start checks, resources and absences. Click a result to open the relevant record; press `Ctrl+K` (or `Cmd+K`) anywhere. `/` also opens search outside an editing field.
- **Project hub**: read-only overview from the sidebar, global search and Gantt labels, linking to the original quotation, itemised costs, cash, readiness, programme and specific activities. No duplicate records.
- **Direct drill-down**: Overview actions from project budget and archived registers; Gantt project names are clickable.
- **Mobile navigation**: visible Section selector accesses all nine modules. Wide spreadsheets still scroll within their panels.
- **Cashflow performance**: aggregates all cash events once per forecast, returning the same values as the original calculation.
- **Smaller app**: original company logo converted to pixel-identical lossless WebP, ~40% reduction in full HTML file size.
- **OneDrive race protection**: does not auto-replace browser data if editing starts or local changes are saved while the cloud download is running.
- **Unsynced exit warning**: warns where supported if local edits are not confirmed saved to OneDrive.
- **No data migration**: existing company backup schema and Microsoft configuration preserved.

## Safe upgrade

1. On your existing v2.5 app, use **Backup all** and store the downloaded JSON in your private company files. Application code updates do not modify OneDrive company data.
2. Refresh https://fixmendmedway.github.io/FMM_Operations/ and verify the sidebar shows **V2.6**.
3. Check **OneDrive** status. Save or back up unsynced local data before downloading/replacing it with the cloud copy.
4. Test **Find anything** via sidebar or `Ctrl+K`, search for a known job reference, open its **Project hub** and follow the **Itemised costs** link.
5. Test a small edit, **Save to OneDrive**, and retrieve it from a second browser, then carry on with ordinary workflows.

## Privacy and limitations

- GitHub is **public code only**: never commit customer records, company JSON backups, Microsoft credentials/tokens or private exports.
- Company data remains in local browser storage and the authenticated Microsoft account's private **OneDrive app folder**. Search stays local.
- OneDrive uses ETag-conditional writes. It does not merge simultaneous edits; work in **one browser at a time** and retain independent dated backups.
- Browser refresh tokens expire; when renewal fails, reauthenticate without discarding local data.
- **QuickBooks is the source of truth** for invoices, customer payments and tax; FMM Operations is for job planning, costing and forecasts.
- External document links must have separate access controls; real Microsoft sign-in and printers need user acceptance testing.
- Automated browser QA used synthetic company records and mocked Microsoft Graph/OAuth; no real customer database was accessed.

## Screens

1. Dashboard — current jobs, alerts, readiness, Gantt and financial outlook.
2. Pricing & quotations — editable Groups, itemised material/labour costs, budgets, markup and conversion.
3. Project budgets — quoted, actual, still-to-spend and variance.
4. Completed archive — archive/restore with original records.
5. Master programme — cross-project schedule and clashes.
6. Individual project — tasks, Gantt, cash events, readiness and links.
7. Resources — capacities, assignments, absence blocks and clashes.
8. Cashflow — monthly receipts/outgoings, recurrence and exports.
9. Readiness — pre-start checks and blockers.

## Rollback

v2.5 remains at branch `backup/v2.5-pre-v2.6`; v2.4 also has a fallback branch. Rolling back application code does not roll back business data stored in OneDrive.
