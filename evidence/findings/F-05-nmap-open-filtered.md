# F-05 — Inconclusive Nmap NULL-Scan States

**Status:** Observed; not a confirmed open-port finding  
**Evidence:** `../evidence/screenshots/page-08.jpg`

## Observation
The Nmap NULL scan (`-sN`) displays several TCP ports as `open|filtered`.

## Interpretation
This state means Nmap could not distinguish an open port from a filtered one using this probe. It must not be reported as a confirmed open service.

## Recommended validation
Use an authorized SYN or TCP connect scan with service/version detection in the isolated lab, and retain the raw output for reproducibility.
