# F-01 — Blank-Credential SMB Enumeration Session

**Status:** Observed in captured evidence  
**Evidence:** `../screenshots/page-03.jpg`

## Observation
The enum4linux output reports that a session was established using blank username and password values during the tested enumeration path.

## Security significance
If an SMB server permits unauthenticated or null-session queries, a network-reachable client may be able to obtain information that should be restricted. The exact impact depends on which RPC/SMB operations and resources are accessible.

## Evidence limitation
This does not, by itself, prove administrative access, arbitrary file access, or write permissions. Do not describe it as full anonymous access to the server.

## Recommended remediation
Review anonymous/null-session settings and restrict anonymous access to the minimum required. Enforce authentication and least privilege; validate from an unauthenticated client after changes.
