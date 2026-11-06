# FMM Operations v2.8.1 — Continuity and OneDrive safety

Live app: https://fixmendmedway.github.io/FMM_Operations/

## Maintenance changes

- **Critical:** OneDrive change detection now includes all seven operational registers introduced in v2.7: mileage, labour, expenses, variations, site notes, document links and job templates. Previously a change affecting only these arrays could escape automatic syncing or conflict checks.
- OneDrive's remote replacement comparison now covers those registers as well; a manual replacement is not silently accepted just because projects/quotes have not changed.
- Readiness alerts open the corresponding project's Readiness page. Resource-clash alerts open Resources & clashes.
- Complete ZIP exports contain **21 files**: a full JSON restore backup, the existing CSV summaries and additional CSVs for mileage, labour, materials/business costs, variations, notes, document links and templates.
- Consistent v2.8.1 version text in the document title and branding.
- **No company database schema changes**, accounting integrations, invoices, payment documents or changes to quotation formulas.

## Required safe upgrade

1. Before refreshing the current app, select **Backup all** in Firefox and Edge, keeping separate private JSON backups.
2. Decide which browser holds your newest changes. If it has unsynchronised mileage or job records, **Save to OneDrive manually** from that browser. Stop and review if a conflict is reported.
3. Open v2.8.1 in both browsers. Do not upload old v2.8 snapshots after switching.
4. The stricter sync fingerprint may initially display **local edits not uploaded**, even where the previous version reported saved. In the master browser, check that the OneDrive ETag is still trusted, then manually **Save to OneDrive** to establish the upgraded baseline. Do not select Load if the local browser has newer entries.
5. Load from OneDrive in the second updated browser. Verify a mileage entry and a site note, then make another dated backup.
6. Edit from **one browser at a time**. OneDrive snapshot sync is not live collaboration.

## Verification

88 automated checks passed across pure JS business logic with synthetic fixtures, mocked Microsoft Graph, simulated form saves, and static UI/source inspections. ZIP generation and 21-member archive integrity were separately verified.

**Limits:** Managed Chromium policy prevented launching local test pages. Real visual browser interaction, Microsoft sign-in and physical printer output were not exercised; a short live acceptance test is still necessary.

Rollback source: `backup/v2.8-before-v2.8.1-audit`. Rolling back code does not undo OneDrive data changes. Public GitHub contains no company data.

For background on tax-year mileage estimates, see https://www.gov.uk/simpler-income-tax-simplified-expenses/vehicles.
