# FMM Operations v2.7 — regression verification

**Automated tests used synthetic data and mocked browser storage; no private company data was accessed.**

## Daily-work register tests — 22/22 passed
- Startup and project selection; daily workspace renders.
- Labour hours x cost rate correctly update an existing quotation actual, retaining existing manual costs; editing labour updates this cost.
- Linked material entries update budget actual; deletion reverses only the logged portion.
- General business outlay, claimant and personal-funds classification persist.
- 2026/27 UK mileage rate uses 55p for first 10,000 then 25p; 2025/26 uses 45p.
- Multiple car/van registrations consume **one** 10,000-mile first-tier allowance for the same claimant.
- Mileage form, rate calculation, print area and CSV export.
- Approved scope variation adjusts job outlook; document link and notes saved and searchable.
- Repeat-job template and local JSON backup include new registers.
- Cold reload restores all new work/mileage/expense/variation/document/template entries.
- No browser JavaScript errors.

## Whole-product integration tests — 20/20 passed
- Existing nine screens plus new Daily Work and Mileage render cleanly.
- New-record migration roundtrip retains entries; older v2.6.1-format backup imports.
- Claimant filtering shows correct mileage and personally paid costs.
- A4 combined costing summary totals mileage and personal outlays separately and together.
- Claim CSV export.
- Mobile section selector contains both new screens and successfully navigates at 390px width.
- No JavaScript errors.

## Additional static checks
- Entire inline JavaScript passes Node syntax validation.
- Public HTML does not contain known private client names/backup data.
- GitHub blob hash verified byte-for-byte against tested HTML.
- v2.6.1 code retained on `backup/v2.6.1-pre-v2.7`.

## Limits to this verification
- Real Microsoft OneDrive cross-browser authentication, cloud save and load were not exercised in this run.
- Physical A4 printer output and tax eligibility were not independently audited.
- The app remains single-writer local-first; older versions must not save snapshots containing v2.7 registers.
