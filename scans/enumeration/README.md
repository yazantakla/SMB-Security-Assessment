# SMB Enumeration Evidence

## Evidence sources
- `../../evidence/screenshots/page-01.jpg` and `page-02.jpg` — anonymous `smbclient` interaction and directory listing.
- `../../evidence/screenshots/page-03.jpg` — enum4linux summary, target/workgroup and enumeration results.
- `../../evidence/screenshots/page-04.jpg` — user/group/RID enumeration output.
- `../../evidence/screenshots/page-05.jpg` — SMB/Samba service information.
- `../../evidence/screenshots/page-06.jpg` — share listing / SMB connection output.
- `../../evidence/screenshots/page-07.jpg` — additional SMB enumeration output.
- `../../evidence/screenshots/page-09.jpg` and `page-10.jpg` — enum4linux user/group-related output.

## Evidence-derived observations
- Target address shown: `192.168.10.20`.
- Workgroup/domain label shown: `WORKGROUP`.
- Server name shown: `METASPLOITABLE`.
- Samba version string shown: `Samba 3.0.20-Debian`.
- The enum4linux output reports a successful session using blank username/password in the tested enumeration path.
- The share listing includes `print$`, `tmp`, `opt`, `IPC$`, and `ADMIN$`.
- The screenshots show user/group names and RID-related enumeration output.
- An `smbclient` anonymous session displays directory-listing output. The screenshot alone does not establish the access permissions of every listed share or the sensitivity of the listed files.

## Limitations
These notes summarize visible screenshot evidence; they are not substitutes for raw logs. Share-level read/write permissions, account validity, and password-policy values must not be overstated beyond what the captured output demonstrates.
