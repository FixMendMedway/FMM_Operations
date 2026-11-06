# FMM Operations v2.8 — Regression QA

Automated desktop/mobile browser checks used synthetic company data with stubbed local/session storage. No live OneDrive or customer records were read.

| Test | Result |
|---|---|
| Full JavaScript syntax validation (Node) | PASS |
| New dashboard empty and populated | PASS |
| Counts unconverted quotations independently of quoted projects | PASS |
| KPI → filtered list → project details → five tabs | PASS |
| Back to list, Close and Escape | PASS |
| Direct opening of original quote, budget, mileage, site record and programme | PASS |
| Read-only drill-down leaves all project/company JSON unchanged | PASS |
| Existing 11 modules render without JavaScript errors | PASS |
| Existing navigation, Ctrl+K search, backup/export, New quote and OneDrive buttons retained | PASS |
| FMM logo returns to Overview | PASS |
| 150 synthetic jobs and 1,200 mileage trips render correctly | PASS |
| Desktop 1440px and mobile 390px/320px; no mobile horizontal page overflow | PASS |
| Public source checked for private customer records | PASS |

**Not tested live:** Microsoft Graph/OAuth, simultaneous editors, site-level authentication, physical printers or connected cloud documents. No data schema or cloud sync logic was changed.
