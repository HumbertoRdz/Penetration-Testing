# Dormitory Web Application Penetration Test

## Overview
This repository documents a web application penetration test conducted as part of a cybersecurity project at Czech Technical University in Prague.  
The goal was to assess the security posture of a student dormitory management platform, following OWASP Testing Guide v4.2 methodologies.

The testing revealed multiple critical, high, and moderate vulnerabilities, providing a real-world learning experience in web security, vulnerability assessment, and responsible reporting.

## Disclaimer
> This report was created for academic purposes.  
> Some vulnerabilities discovered during the engagement may remain unpatched.  
> No detailed exploitation steps or sensitive technical data are disclosed to maintain responsible disclosure practices.  
> No active exploitation was performed beyond authorized testing.

## Scope
- External black-box web application penetration test.
- Focused on a university-managed dormitory web platform.
- Testing window: April-May 2024.
- Authorized access using valid credentials.

## Key Findings (Summary)

| Vulnerability | Severity | Description |
|---------------|----------|-------------|
| Admin Panel Access via Client-Side Role Manipulation | High | Role change in local storage grants admin panel UI access without privileged actions. |
| Sensitive Information Sent via Unencrypted Channels | Critical | User credentials transmitted in plaintext in POST request. |
| Session Hijacking (Replay Attack) | Critical | Session replay vulnerabilities found — logging in using another user's token. |
| Public Information Leakage through API | High | Sensitive user data (address, email, name) accessible without authentication. |
| Session Fixation | High | JWT tokens not invalidated on logout. |
| Cross-Site Request Forgery (CSRF) | High | Password change functionality vulnerable. |
| Weak Lockout Mechanism and Default Passwords | High | No protection against brute-force login attempts; multiple accounts kept default weak passwords. |
| Exposed Session Variables | Medium | Session IDs exposed in HTTP responses (only own session observed). |
| Weak Password Policy | Moderate | Passwords like "12345678" accepted without enforcement of complexity. |
| User Enumeration | Moderate | Different error responses reveal valid emails. |
| Lack of HSTS Header | Moderate | Missing strict transport enforcement (HSTS). |

## Tools Used
- Burp Suite
- OWASP ZAP
- Nmap
- SQLmap
- Hydra
- Custom Python scripts

## Methodology
- Information gathering and passive reconnaissance
- Vulnerability assessment following OWASP Testing Guide v4.2
- Manual testing and exploitation within authorized scope
- Session management and token replay analysis
- API endpoint testing

## Lessons Learned
- Importance of enforcing server-side authorization controls
- Critical risks from poor session management and token handling
- Need for encrypting sensitive data transmissions (TLS enforcement)
- Practical application of ethical responsible disclosure practices

## Author
**Humberto Rodríguez Ruán**  
Cybersecurity Student | Cloud Enthusiast | Application Security Practitioner  
[LinkedIn Profile](https://www.linkedin.com/in/humberto-rodr%C3%ADguez-ru%C3%A1n-437493209/)
