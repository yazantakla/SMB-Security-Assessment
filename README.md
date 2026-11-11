# SMB Security Assessment & Internal Network Enumeration

> A controlled-lab assessment of SMB exposure and information disclosure using Kali Linux against a Metasploitable target.

## Project overview

This project documents a hands-on assessment of SMB-related services in an isolated virtual lab. The work focuses on host discovery, SMB service identification, anonymous/null-session behavior, share enumeration, user and group enumeration, and the security implications of information exposed to an unauthenticated or low-privilege network client.

**Assessment status:** Initial evidence collection documented; validation and remediation analysis are in progress.

## Scope and authorization

- **Environment:** Isolated virtual lab (VirtualBox)
- **Assessment workstation:** Kali Linux
- **Target:** Metasploitable lab host
- **Observed target address:** `192.168.10.20` (private lab address; may differ in another setup)
- **Observed service:** Samba `3.0.20-Debian`
- **Authorization:** Testing is limited to systems owned by the operator or explicitly authorized for testing. Do not run these techniques against public or third-party systems.

## Tools observed in the evidence

- Nmap 7.95
- enum4linux 0.9.1
- smbclient

## Assessment workflow

1. Discover live hosts in the lab subnet.
2. Identify SMB-related ports and services.
3. Test whether a null/anonymous session is accepted.
4. Enumerate available SMB shares.
5. Enumerate domain/workgroup and user/group information where exposed.
6. Assess the security impact of the observed information disclosure.
7. Validate findings and document practical remediation steps.

## Initial observations

The screenshots currently included in `evidence/screenshots/` support the following observations:

| Area | Evidence-based observation | Interpretation / limitation |
|---|---|---|
| Host discovery | The scan identified `192.168.10.20` as up. | Applies only to the recorded lab run. |
| SMB identity | enum4linux reported `METASPLOITABLE` and `Samba 3.0.20-Debian`. | Version identification is recorded from the tool output; verify independently before making a vulnerability claim. |
| Session behavior | enum4linux reported that the server allowed a session with blank username and password. | Indicates null-session/anonymous access behavior for the tested enumeration path; exact permissions must be tested per share and operation. |
| Workgroup | `WORKGROUP` was reported. | Environment metadata disclosure. |
| Shares | The output listed `print$`, `tmp`, `opt`, `IPC$`, and `ADMIN$`. | Listing a share does not by itself prove read or write access. Access levels require separate validation. |
| Account enumeration | User/group names and RIDs were returned through enumeration. | Information disclosure; do not assume every returned name is an enabled or interactive human account. |
| Password policy | The captured output reported password complexity disabled, but the displayed minimum-length values are inconsistent across sections. | Treat password-policy details as **unverified** until a fresh, repeatable check is captured. |
| Nmap `-sN` output | Several ports were labelled `open|filtered`. | This scan state is inconclusive; it does not establish that those services are open. Use a suitable TCP connect or SYN scan and service detection to validate. |

## Repository structure

```text
SMB-Security-Assessment/
├── README.md
├── LICENSE
├── .gitignore
├── docs/
│   ├── methodology.md
│   ├── technical-analysis.md
│   └── remediation.md
├── scans/
│   ├── README.md
│   ├── nmap/README.md
│   └── enumeration/README.md
├── evidence/
│   ├── README.md
│   ├── screenshots/
│   └── findings/
│       ├── README.md
│       └── F-01 ... F-06
└── reports/
    └── security-assessment.md
```

## Evidence handling and reproducibility

The supplied screenshots are treated as the primary evidence for this project because they document the original lab execution. Structured notes under `scans/` and finding records under `evidence/findings/` are derived from those screenshots and link back to them. They are explicitly labelled as summaries, not raw tool logs. No raw output has been invented. Replace lab IP addresses and interface details if reproducing the work in another isolated environment.

## Current limitations

- The repository contains screenshot evidence and structured summaries, but not raw `.nmap`, `.gnmap`, `.xml`, or text logs.
- Share read/write permissions have not been established for every listed share.
- Password-policy values require caution because the captured output is inconsistent.
- No CVE or exploitability claim is made solely from the reported Samba version.

## Disclaimer

This repository is for education and authorized security testing only. The author does not support unauthorized access, disruption, data theft, or testing systems without permission.

## Author

**Yazan Takla** — Cybersecurity / Network Security Portfolio
