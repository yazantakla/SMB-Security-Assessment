# Nmap Evidence

## Evidence source
- `../../evidence/screenshots/page-08.jpg` — Nmap TCP NULL scan (`-sN`) against `192.168.10.20`.

## Recorded observations
- Target shown: `192.168.10.20`.
- The host was reported as up.
- The scan output labels multiple TCP ports as `open|filtered`.
- The screenshot reports that 256 IP addresses were scanned and 2 hosts were up.

## Interpretation
`open|filtered` is an ambiguous Nmap state for this scan type. It does **not** prove that the listed services are open. This evidence is useful as an initial reconnaissance artifact only; it should not be presented as confirmed service exposure.

## Reproduction note
The screenshot shows `nmap -sN 192.168.10.20`. No raw `.nmap`, `.gnmap`, or `.xml` output was present in the supplied evidence package, so none is fabricated here.
