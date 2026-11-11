# SMB Security Assessment Report

## Executive summary

An initial SMB assessment was performed against a Metasploitable host in an isolated VirtualBox lab. The captured evidence identifies Samba `3.0.20-Debian`, reports successful blank-credential session behavior during enum4linux checks, lists several SMB shares, and returns user/group information.

These observations indicate potential SMB information disclosure. The current evidence does **not** establish that every listed share is readable or writable, that administrative access is available, or that a specific CVE is exploitable.

## Scope

- Target: Metasploitable lab host
- Observed address: `192.168.10.20`
- Tools: Nmap 7.95, enum4linux 0.9.1, smbclient
- Environment: isolated VirtualBox lab

## Findings register

| ID | Finding | Current confidence | Status |
|---|---|---|---|
| F-01 | Null-session / anonymous enumeration behavior | Medium; requires repeat validation | Open |
| F-02 | SMB share names disclosed | High for visibility; permissions unknown | Open |
| F-03 | User/group information disclosed | Medium; validate exact enumeration path | Open |
| F-04 | Legacy Samba version identified | Medium; verify exact build/support status | Open |
| F-05 | Password-policy configuration | Low; captured values conflict | Needs retest |

## Conclusion

The initial evidence supports further investigation of anonymous SMB enumeration, share permissions, and service lifecycle. Complete the validation items before assigning final severity or claiming exploitability.

## Evidence index

See `../evidence/screenshots/` for the original captured screenshots. Add raw command output under `../scans/` during the repeatable validation phase.
