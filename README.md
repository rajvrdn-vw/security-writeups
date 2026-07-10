# security-writeups

# Server-Side Vulnerabilities - PortSwigger Web Security Academy
Notes from working through PortSwigger's Server-side vulnerabilities path. Used Burp Suite Community on Kali (VirtualBox) for all of it.
 
15 labs, 6 categories:
 
| # | Lab | Category |
|---|-----|----------|
| 01 | [File path traversal, simple case](01-file-path-traversal-simple-case.md) | Path Traversal |
| 02 | [Unprotected admin functionality](02-unprotected-admin-functionality.md) | Access Control |
| 03 | [Unprotected admin functionality, unpredictable URL](03-unprotected-admin-functionality-unpredictable-url.md) | Access Control |
| 04 | [User role controlled by request parameter](04-user-role-controlled-by-request-parameter.md) | Access Control |
| 05 | [User ID controlled by request parameter, unpredictable IDs](05-user-id-controlled-by-request-parameter-unpredictable-user-ids.md) | Access Control (IDOR) |
| 06 | [User ID controlled by request parameter, password disclosure](06-user-id-controlled-by-request-parameter-password-disclosure.md) | Access Control (IDOR) |
| 07 | [Username enumeration via different responses](07-username-enumeration-via-different-responses.md) | Authentication |
| 08 | [2FA simple bypass](08-2fa-simple-bypass.md) | Authentication |
| 09 | [Basic SSRF against the local server](09-basic-ssrf-against-local-server.md) | SSRF |
| 10 | [Basic SSRF against another back-end system](10-basic-ssrf-against-another-backend-system.md) | SSRF |
| 11 | [RCE via web shell upload](11-rce-via-web-shell-upload.md) | File Upload |
| 12 | [Web shell upload via Content-Type bypass](12-web-shell-upload-content-type-bypass.md) | File Upload |
| 13 | [OS command injection, simple case](13-os-command-injection-simple-case.md) | OS Command Injection |
| 14 | [SQLi in WHERE clause, hidden data](14-sqli-where-clause-hidden-data.md) | SQL Injection |
| 15 | [SQLi login bypass](15-sqli-login-bypass.md) | SQL Injection |
