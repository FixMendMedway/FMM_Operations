# FMM Operations v2.7 — Daily Work & Mileage

**Fix & Mend Medway** — [Open the live application](https://fixmendmedway.github.io/FMM_Operations/)

v2.7 remains an **operational and job-budgeting tool**, not an accounting system. No QuickBooks connection, invoice generation, payment chasing, online payments or financial documents beyond operating budgets and user-requested mileage/costing sheets have been added.

## What's new

- **Daily Work**: one project workspace with quick actions for labour, materials, mileage, notes, document links and scope variations. Links to existing original quotation, costing, tasks, readiness and Gantt.
- **Labour logs**: worker, date, hours, cost rate and linked quotation cost line. Linked logs update the line's actual cost without double-counting existing manual actuals. Edit/delete adjusts only the logged portion.
- **Materials and operating expenses**: record project or general-business costs, paid through the business or personally, with an optional HTTPS evidence link; allocate a cost against an existing quotation cost item.
- **Variations**: proposed, approved or rejected. Approved extra sale value and projected cost affect adjusted job outlook without modifying the signed original quote or generating an invoice.
- **Mileage & Business Costs**: log job-specific and general business miles with date, claimant, vehicle registration/type, origin, destination and business reason. Tax year 6 April–5 April; tax-year/job/claimant filters; CSV export; printable A4 mileage sheet and combined personally paid cost summary.
- **HMRC rate estimates**: 2026/27 55p for the first 10,000 car/van miles across relevant cars/vans for each claimant, then 25p; 2025/26 and earlier 45p then 25p; motorcycle 24p. Post-2026/27 rates are provisional until confirmed. Custom-rate trips are estimates only and do not consume HMRC mileage bands.
- **Document links**: store HTTPS private document links against projects; no document bytes are uploaded to GitHub.
- **Repeat-job templates**: copy task and readiness structures without copying customer details, recorded costs or cash transactions.
- **Search & mobile**: new records included in universal search, all 11 areas available from existing desktop menu and mobile section selector.

## REQUIRED SAFE UPGRADE FROM v2.6.1

1. In **every browser** previously used, click **Backup all** and keep separate dated JSON files outside the public GitHub repo.
2. Confirm your latest local edits have successfully saved to OneDrive; do not overwrite unsynced local data.
3. Refresh **Firefox and Edge** to show **FMM OPERATIONS · V2.7** *before entering any mileage, cost or site log records*. Older v2.6.1 code cannot preserve v2.7's new register arrays if it saves a cloud snapshot.
4. In an up-to-date v2.7 browser with no unsynced changes, **Load from OneDrive**, confirm the familiar projects and quotation totals, add one small test mileage entry and Save to OneDrive.
5. In the second **v2.7** browser, load the cloud data and verify the test entry, then back up again.
6. Use one browser for edits at a time. OneDrive's ETag-based snapshot sync prevents silent overwrites but does not merge simultaneous edits.

## Tax and data limitations

- **This is a mileage record/cost estimate, not an automatic tax deduction, invoice, reimbursement or tax filing.** Ordinary commuting is generally ineligible. Simplified mileage generally replaces actual running costs for that vehicle; other vehicle eligibility and prior capital allowances matter.
- Claimant and vehicle information are recorded for evidence; custom rate is an internal cost assumption. Do not mix incompatible tax methods for one vehicle.
- Existing cashflow and previously available export/print tools remain as they were; there is no new accounting integration.
- Company data lives in private OneDrive JSON and local browser storage. Public GitHub contains app code only.
- Keep dated JSON backups. The fallback code branch is `backup/v2.6.1-pre-v2.7`, but older code is **not safe to edit new v2.7 data**.
- Live Microsoft Graph sign-in, OneDrive account acceptance and physical printer output were **not** exercised by the automated browser tests.

Mileage rates: [HMRC simplified expenses](https://www.gov.uk/simpler-income-tax-simplified-expenses/vehicles); [ITTOIA 2005 section 94F](https://www.legislation.gov.uk/ukpga/2005/5/section/94F).
