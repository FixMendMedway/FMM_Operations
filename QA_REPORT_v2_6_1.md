# FMM Operations v2.6.1 — status/archive QA

## Browser tests completed (synthetic records)
- Set status to Completed using the Projects & Budgets inline dropdown: status and archive date saved together; project moves into Completed archive — PASS.
- Open a completed archived job and change its status to Active: archive date cleared; project returns to current list — PASS.
- Change status to Completed using the Edit Project modal: archive date saved in the same operation — PASS.
- Use Restore on a completed archived job: returns to current list as Active — PASS.
- Identify older Completed jobs without archivedAt and archive them using the explicit one-click action — PASS.
- Status selector available in the individual project view, project hub, current-job sidebar and project registers — PASS.
- Decline the Completed confirmation: no status/archive changes saved — PASS.
- Reload application using persisted browser storage: completed/archived status retained — PASS.
- Render all nine existing screens after the change: no JavaScript errors — PASS.
- On a 390px mobile viewport, change a project to Completed; archive view selected; quoted value, project notes and recorded cash left intact — PASS.
- Node JavaScript syntax validation — PASS.

## Safety
- All data in QA fixtures was synthetic; **no real OneDrive company data was loaded or modified**.
- Cloud ETag protection and Microsoft authentication are untouched.
- The GitHub code contains no customer backups.
- Existing project data/schema and quotation, cash, Gantt, cost records and imports are unchanged.
- Real Microsoft account testing is still required to confirm cross-device delivery.
- v2.6 is backed up in branch `backup/v2.6-pre-status-hotfix`.
