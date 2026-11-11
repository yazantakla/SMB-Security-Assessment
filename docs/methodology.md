# Assessment Methodology

## 1. Objective

Assess SMB exposure on the authorized Metasploitable lab host and determine what information can be obtained through unauthenticated or null-session enumeration.

## 2. Environment

- Kali Linux assessment machine
- Metasploitable target
- VirtualBox isolated network
- Target observed in the evidence: `192.168.10.20`

## 3. Phases

### 3.1 Host discovery

Identify active hosts in the private lab subnet. Preserve the exact command, timestamp, interface, and raw output when repeating the scan.

### 3.2 Service discovery

Identify TCP/139 (NetBIOS Session Service) and TCP/445 (Microsoft-DS/SMB) using an appropriate TCP scan. A Null scan (`-sN`) can produce `open|filtered`; this state is ambiguous and must not be reported as confirmed open.

### 3.3 SMB session check

Test the server's response to a null/anonymous session using the approved lab tools. Record whether session setup succeeds and what operations are permitted.

### 3.4 Share enumeration

List visible shares, then test each share separately for listing/read/write permissions. Do not infer permissions from share names or visibility alone.

### 3.5 User and group enumeration

Record disclosed account names, RIDs, and group information. Distinguish local users, domain/workgroup groups, service accounts, and built-in accounts where the output supports that distinction.

### 3.6 Policy review

Collect password-policy information and repeat any inconsistent result. Record tool version and command options so the observation is reproducible.

### 3.7 Reporting

For every finding, document evidence, affected asset, security impact, confidence, limitations, and remediation.
