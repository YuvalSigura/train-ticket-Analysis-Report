# Train Ticket — Penetration Testing & Security Assessment

Public portfolio project demonstrating hands-on web/API security assessment, vulnerability validation, proof-of-concept (PoC) reporting, impact analysis, and remediation guidance against the open-source FudanSELab Train Ticket microservices application.

**Report author:** Yuval Sigura  
**Assessment report:** [train-report.pdf](./train-report.pdf)  
**Original project:** https://github.com/FudanSELab/train-ticket

## What this project demonstrates

- Web and API penetration-testing methodology
- Vulnerability assessment and manual validation
- Reproducible technical evidence and PoC demonstrations
- OWASP Top 10:2021 mapping
- Security impact and risk prioritization
- Actionable remediation guidance
- SAST, DAST, network reconnaissance, and DevSecOps security tooling

## Selected findings

| Finding | OWASP Top 10:2021 | Evidence status |
|---|---|---|
| Broken Access Control / IDOR | A01 — Broken Access Control | Confirmed PoC |
| CSRF protection disabled | A01 — Broken Access Control | Configuration evidence / PoC |
| Server-side injection behavior | A03 — Injection | Validated behavior |
| Client-side injection / XSS risk | A03 — Injection | Code/configuration evidence |
| Security headers, CORS and cookie issues | A05 — Security Misconfiguration | Configuration evidence |
| Hardcoded credentials | A07 — Identification and Authentication Failures | Source-code evidence / PoC |
| SSRF-related risk | A10 — Server-Side Request Forgery | Security analysis; not presented as a confirmed exploit |

The public report deliberately distinguishes confirmed exploitation evidence from analysis-only findings.

## Tools and techniques

- Burp Suite Professional
- Nmap
- SonarQube
- CodeQL
- Docker Scout
- Shodan
- Manual web/API testing
- Static analysis and vulnerability scanning
- Impact analysis and remediation reporting

## Report structure

The report includes:

1. Executive summary
2. Scope and methodology
3. Risk overview
4. Detailed findings
5. Technical evidence / PoC where available
6. Impact analysis
7. Remediation recommendations
8. OWASP/CWE taxonomy notes
9. Tooling and references

## Portfolio note

This repository is a public, sanitized portfolio artifact intended to demonstrate penetration-testing workflow and technical reporting. Sensitive or unnecessary live-target details are not included.

## Ethics

Testing and analysis are intended for authorized, educational, and research environments only. The assessed application is an open-source project used as a security-testing target in a controlled context.
