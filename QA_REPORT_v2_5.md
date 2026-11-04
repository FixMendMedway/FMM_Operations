# FMM Operations v2.5 — verification

Tests performed on the clean, customer-data-free `index.html` release.

## Browser and integration tests

| Check | Result |
|---|---|
| Chromium loads the application with all nine navigation screens | PASS |
| No JavaScript errors in the test workflow | PASS |
| Import/download establishes a trusted cloud baseline | PASS |
| Local edit tracked as unsynced and saved with conditional ETag | PASS |
| Expired Microsoft access token renewed via mock refresh-token endpoint | PASS |
| Newer cloud version safely loaded when local data is unchanged | PASS |
| Local and remote edits generate a blocked conflict | PASS |
| Conflict review and two-confirmation local-master recovery | PASS |
| Auto-upload after local edit updates simulated OneDrive | PASS |
| HTTP 412 precondition failure blocks overwrite and sets conflict | PASS |
| Reauthentication retains the trusted ETag and local company data | PASS |
| Node JavaScript syntax validation | PASS |
| Clean public code contains no imported customer names or records | PASS |

Tests used a controlled simulated Microsoft Graph server, synthetic authentication responses and browser-storage stubs. No live customer OneDrive data was accessed. Real Microsoft sign-in, cross-browser acceptance and post-deployment printing must be checked by the user. Print/PDF and Gantt code paths are unchanged from the previously tested v2.4.

The previous version is retained at `backup/v2.4-pre-sync-upgrade`. Do not commit any JSON company backups.
