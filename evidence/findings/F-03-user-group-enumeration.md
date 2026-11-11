# F-03 — User and Group Information Disclosure

**Status:** Enumeration output observed  
**Evidence:** `../screenshots/page-04.jpg`, `../screenshots/page-09.jpg`, `../screenshots/page-10.jpg`

## Observation
The captured enum4linux output contains user/group-related names and RID values.

## Security significance
Account and group metadata can support username discovery, targeted password attacks, and social-engineering preparation. The presence of a name in enumeration output does not prove that the account is enabled, interactive, or usable for authentication.

## Recommended remediation
Restrict anonymous enumeration where operationally possible, remove stale accounts, use strong authentication controls, and monitor repeated account-enumeration activity.
