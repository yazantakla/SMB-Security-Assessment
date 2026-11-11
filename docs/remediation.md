# Remediation Recommendations

Recommendations below are defensive guidance. Confirm the actual configuration and operational requirements before applying changes.

1. **Disable unnecessary anonymous/null-session access.** Restrict anonymous IPC/RPC enumeration where it is not required.
2. **Apply least privilege to SMB shares.** Review share-level and filesystem-level ACLs; remove broad guest or Everyone permissions unless explicitly required.
3. **Restrict network exposure.** Permit TCP/445 and TCP/139 only from trusted network segments and required management hosts. Block SMB at internet boundaries.
4. **Modernize the SMB service.** Upgrade unsupported Samba/OS components to a currently supported release and apply security updates.
5. **Harden authentication.** Enforce strong password policy, account lockout controls where appropriate, and modern authentication practices.
6. **Reduce information disclosure.** Limit unnecessary user/group enumeration and server/banner metadata exposure.
7. **Monitor SMB activity.** Log authentication failures, anonymous access attempts, share access, and unusual enumeration patterns.
8. **Retest after remediation.** Repeat the same checks and compare results to the original evidence.
