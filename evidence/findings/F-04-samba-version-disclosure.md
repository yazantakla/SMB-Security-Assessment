# F-04 — Samba Version String Disclosure

**Status:** Version string observed; vulnerability status not assessed  
**Evidence:** `../evidence/screenshots/page-05.jpg`

## Observation
The captured service-information output identifies `Samba 3.0.20-Debian`.

## Security significance
A legacy version string can help defenders identify software requiring lifecycle review. Version disclosure alone is not proof that a specific CVE applies or is exploitable in this environment.

## Recommended remediation
Confirm the installed package and vendor patch status on the host, upgrade to a supported Samba release where possible, and restrict SMB exposure to trusted network segments.
