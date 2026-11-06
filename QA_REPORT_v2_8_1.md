# FMM Operations v2.8.1 — Full synthetic-data regression audit

## Result

**88 passed, 0 failed** in isolated JS VM and source inspection, plus **21-file ZIP integrity verification**.

| Test suite | Passed | Failed |
|---|---:|---:|
| Functional calculations, all 11 sections, dashboard drill-down, archive and performance stress | 44 | 0 |
| Simulated Microsoft Graph uploads, ETag conflicts and replacement prompts | 9 | 0 |
| Form submission and full job workflows | 19 | 0 |
| HTML, safety, metadata and code structure | 16 | 0 |
| **Total** | **88** | **0** |

## Root cause found and resolved

The v2.8 `fmmCloudDataFingerprint` considered projects, quotations and settings but **not** mileage, labour, logged purchases, scope variations, notes, document links or templates. Auto-upload might therefore miss a new trip or work log. Conflict detection could classify a locally modified register as clean. A manual cloud download also compared only the legacy fields, risking replacement without prompting.

v2.8.1 includes the full seven-register fingerprint both in upload/sync status and remote-difference checks. The new tests separately exercised:
- Mileage-only local changes reported unsynced.
- Conditional upload puts the new trip into the cloud snapshot and advances the ETag.
- A remote-only mileage change is detected.
- Simultaneous changes are blocked without replacing remote content.
- Manual load differing only in these registers demands confirmation; cancellation preserves local records.

All Graph responses were mocked. No live Microsoft account or private data was accessed.

## Operational integration exercised

- Dashboard KPI → project → overview, costs, programme, site records, mileage.
- Quotations, project budgeting, archive/restore, resources, Gantt, readiness, cashflow and local saved drafts.
- Accepted quotation → active project conversion; duplicate conversion prevented.
- Labour and materials logged to quotation cost lines, no double-counting; proposed/rejected/approved variations.
- 2025/26 and 2026/27 HMRC mileage rates, threshold split, multiple vehicles, motorcycle and custom rates.
- Personal spending claims, mileage print summary and CSV spreadsheet-injection protection.
- Repeat-job templates do not carry customer details; document links enforce HTTPS.
- JSON validation rejects duplicate project IDs and invalid task dates.
- Synthetic stress of 150 extra jobs and 1,200 extra mileage records.
- Complete ZIP export containing full JSON plus 20 supplemental reports: **21 valid files**, seven additional readable CSVs present and populated.

## Limits and acceptance

The available Chromium browser has managed URLBlocklist policy preventing page navigation to even a local test server or file. Consequently HTML was inspected statically, and actual business JS ran in a Node VM with a stub DOM; this does not prove all real clicks, mobile layout, keyboard focus order or physical printing. OneDrive integration was mocked, not connected.

No actual customer records were imported; all fixtures had synthetic `QA-` references and fake clients. The release does not alter company schema or the existing cost formulas.

**User acceptance after publishing:** back up both browsers; manually reconcile the first OneDrive baseline; verify one new mileage entry between updated browsers; verify that a resource-clash alert opens Resources.
