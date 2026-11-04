# FMM Operations v2.5 — safer OneDrive sync

FMM Operations is the Fix & Mend Medway browser application for quotations, editable Groups, itemised labour/material budgets, quote conversion, Gantt schedules, resources, cashflow, readiness and a retrievable project archive.

## Privacy and deployment

- **GitHub Pages hosts application code only.** Do not upload private JSON backups, client records, spreadsheets, receipts, Microsoft credentials or tokens to this public repository.
- Business data remains in the authenticated user's private **OneDrive app folder** or their local browser draft. The code is built as a single `index.html` file.
- The website is https://fixmendmedway.github.io/FMM_Operations/. Its address is also the Azure Entra SPA redirect URI.

## Upgrade from v2.4 (important)

1. In v2.4, select **Backup all** and save a dated local JSON backup, especially before refreshing the website on another computer.
2. Refresh the GitHub Pages app and confirm the sidebar shows **V2.5**. Existing local browser data and the Microsoft Application ID remain stored under the same browser keys.
3. **First-time setup in each browser:** open **OneDrive sync** and **Load OneDrive copy** to establish a trusted cloud baseline. If that browser has newer *unsynchronised* data, back it up before replacing it; reconcile those changes first.
4. Test **Save to OneDrive**, followed by **Check OneDrive** in a second browser. Once both load the expected data, you can enable **Automatically upload changes** if you wish.
5. Do not edit the same company data on two browsers simultaneously. Conflicts are blocked and require choosing a master copy or manually reconciling backups.

## v2.5 improvements

- **Session recovery:** OAuth token renewal using a session-scoped Microsoft refresh token; re-sign-in does not discard the last trusted cloud version.
- **Safe cloud baseline:** OneDrive version ETag, app-folder identity and SHA-256 fingerprint of the last saved company data persisted as non-secret metadata in local browser storage.
- **Automatic checks:** approximately once per minute while signed in, and when the application regains focus.
- **Safe automatic download:** only when the cloud has changed and the browser has no outstanding edits or active form being edited.
- **Conflict protection:** local and remote changes in parallel block uploads; an in-app review gives both backup options and guarded master-copy selection.
- **Conditional saves:** matching OneDrive ETags required to update an existing file. A 409/412 server conflict is treated as unsafe to overwrite.
- **Clear status:** cloud saved, local changes not uploaded, sign-in required, newer cloud copy available, or conflict.

## Technical limits

- This remains a **local-first single-user system**, not multi-user real-time collaboration. Cloud versions are not automatically merged.
- Browser session refresh tokens expire after roughly 24 hours; a new sign-in can still be required. Tokens are not placed in GitHub or persistent localStorage.
- The first v2.5 launch needs a deliberate **Load from OneDrive** if it does not already have a v2.5 trusted baseline.
- Keep regular full JSON/ZIP backups separate from GitHub.
- Automated browser QA used mocked Microsoft Graph/OAuth endpoints, not a real user sign-in. Check the sync status after every first live save.

## Rollback

The pre-upgrade code is preserved at branch `backup/v2.4-pre-sync-upgrade`. The v2.5 release is on `main`.

