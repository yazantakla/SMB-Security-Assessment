# F-02 — SMB Share Names Disclosed

**Status:** Share names observed; permissions not fully established  
**Evidence:** `../screenshots/page-03.jpg`, `../screenshots/page-06.jpg`

## Observation
The captured output lists `print$`, `tmp`, `opt`, `IPC$`, and `ADMIN$`.

## Security significance
Share enumeration reveals the server's exposed SMB namespace and can help an attacker prioritize further probing. A share being listed does not prove that its contents are readable or writable.

## Evidence limitation
The evidence package does not provide a complete per-share access-control matrix. Do not claim that all listed shares are accessible.

## Recommended remediation
Review each share's share-level and filesystem ACLs, remove unnecessary shares, restrict access by role, and verify read/write permissions using separate low-privilege test accounts.
