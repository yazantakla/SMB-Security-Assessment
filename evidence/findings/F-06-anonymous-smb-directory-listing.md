# F-06 — Anonymous SMB Directory Listing

**Status:** Directory-listing output observed for the shown session  
**Evidence:** `../evidence/screenshots/page-01.jpg`, `../evidence/screenshots/page-02.jpg`

## Observation
The `smbclient` screenshots show an anonymous login and directory-listing output for the share/session displayed in the terminal.

## Security significance
Unauthenticated directory listing may expose filenames and directory structure. The risk depends on the actual share, the sensitivity of the contents, and whether file reads or writes are permitted.

## Evidence limitation
Do not generalize the shown listing to every enumerated share. The screenshots do not establish arbitrary write access.

## Recommended remediation
Identify the exact share used, review its ACLs and contents, disable anonymous access unless explicitly required, and retest read and write operations separately.
