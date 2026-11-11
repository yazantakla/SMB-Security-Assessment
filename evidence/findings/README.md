# Findings Register

The findings below are derived from the supplied lab screenshots. Confidence refers to what the current evidence demonstrates, not to the severity of a potential vulnerability.

| ID | Finding | Evidence | Status |
|---|---|---|---|
| F-01 | Blank-credential SMB enumeration session accepted by the tested enum4linux path | `page-03.jpg` | Observed; scope of access requires validation |
| F-02 | SMB share names disclosed | `page-06.jpg`, `page-03.jpg` | Observed; per-share permissions unknown |
| F-03 | User/group and RID information disclosed | `page-04.jpg`, `page-09.jpg`, `page-10.jpg` | Observed in captured enumeration output |
| F-04 | Samba version string disclosed | `page-05.jpg` | Observed; exact patch/build status not independently verified |
| F-05 | Nmap NULL scan returned `open|filtered` states | `page-08.jpg` | Observed; inconclusive for service openness |
| F-06 | Anonymous SMB client directory listing displayed | `page-01.jpg`, `page-02.jpg` | Observed for the shown session/path; do not generalize to all shares |

See the individual finding files for impact, evidence, limitations, and remediation.
