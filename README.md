# 🚆 Train Ticket Security Assessment (OWASP Top 10)

[![OWASP](https://img.shields.io/badge/OWASP-Top%2010-blue)](https://owasp.org/)
[![Pentest Report](https://img.shields.io/badge/Report-Penetration%20Testing-red)](./docs/train-report.pdf)
[![Docker](https://img.shields.io/badge/Infra-Docker%2FKubernetes-green)](https://www.docker.com/)
[![License](https://img.shields.io/badge/License-Educational-lightgrey)]()

---

## 📖 Description
A large-scale, distributed **train ticket booking system** built with **41 microservices**, handling user management, ticket purchasing, and system administration.  
Each microservice is designed for **scalability, fault tolerance, and maintainability**.

This repository documents an **end-to-end application & API security assessment** against the system, focusing on the **OWASP Top 10** with **PoCs, remediation code fixes, and a prioritized mitigation roadmap**.

🔗 [Original project (FudanSELab/train-ticket)](https://github.com/FudanSELab/train-ticket)  
✍️ Report author: **Yuval Sigura**

---

## 🔎 Project in 30 seconds
- **41 microservices**: Java (Spring Boot/Cloud), Node.js (Express), Python (Django), Go (Webgo).  
- **Databases**: MongoDB, MySQL.  
- **Deployment**: Docker, Kubernetes, docker-compose.  
- **SAST**: SonarQube, CodeQL, Docker Scout.  
- **DAST/Manual**: Burp Suite Pro, Nmap.  
- **Recon**: Shodan.  
- **Output**: professional pentest report with PoCs, code fixes, and remediation roadmap.

---

## 📚 Table of Contents
- [Scope](#scope)
- [Methodology](#methodology)
- [Executive Summary of Findings](#executive-summary-of-findings)
- [Detailed Findings](#detailed-findings)
- [Remediation Roadmap](#remediation-roadmap)
- [How to Reproduce (Quick Start)](#how-to-reproduce-quick-start)
- [Artifacts](#artifacts)
- [Ethics & Disclaimer](#ethics--disclaimer)
- [Contact](#contact)

---

## 🎯 Scope
- **In scope**: public APIs & internal services of the Train-Ticket microservices system.  
- **Out of scope**: third-party SaaS unrelated to the repo, social engineering, production data.

---

## 🛠 Methodology

### SAST
- **SonarQube**: code vulnerabilities/bugs/smells across Java/JS/Python/Go.  
- **CodeQL (GitHub Actions)**: security queries per language.  
- **Docker Scout**: base image & dependency CVEs.

### DAST & Manual Testing
- **Burp Suite Pro**: intercept, active/GA scans, manual exploitation.  
- **Nmap**: service discovery & version enumeration.  
- **Shodan**: external attack-surface reconnaissance.

### Infra/Orchestration
- Local deployment via **Docker/Kubernetes** for realistic end-to-end testing.  

---

## 📊 Executive Summary of Findings

| ID   | Category (OWASP 2021)        | Affected Area            | Severity  | Status |
|------|-------------------------------|--------------------------|-----------|--------|
| F-01 | Injection (A03)              | `/api/v1/verifycode`     | 🔴 High   | Open   |
| F-02 | Client-Side Injection (A04)  | `client_collect.js`      | 🔴 High   | Open   |
| F-03 | Broken Access Control (IDOR) | `orderservice` endpoints | 🔴 High   | Open   |
| F-04 | CSRF Disabled (A05)          | Spring Security config   | 🔴 High   | Open   |
| F-05 | Hardcoded Credentials (A02)  | Source code              | 🟣 Critical | Open |
| F-06 | SSRF (A10)                   | URL fetch logic          | 🔴 High   | Open   |
| F-07 | Misconfig (CORS, Headers)    | Multiple services        | 🟠 Medium | Open   |

---

## 📂 Detailed Findings
Detailed PoCs, screenshots, and remediation steps are included in [`docs/train-report.docx`](./docs/train-report.docx).  
Each finding contains:
- **Description** of the issue.  
- **Proof of Concept (PoC)**.  
- **Code snippet** or vulnerable config.  
- **Impact assessment**.  
- **Remediation guidance** with sample fixes.

---

## 🛡 Remediation Roadmap
1. **Immediate**: revoke hardcoded credentials, enable CSRF protection, patch SSRF endpoints.  
2. **Short-term**: add security headers, restrict CORS, sanitize cookies and inputs.  
3. **Mid-term**: CI/CD integration with SonarQube + CodeQL.  
4. **Long-term**: periodic penetration testing and cloud security posture reviews.

---

## ⚡ How to Reproduce (Quick Start)

### 1) Deploy locally
```bash
# Option A: docker-compose (recommended for quick spin-up)
docker compose up -d

# Option B: Kubernetes (if you have manifests)
kubectl apply -f k8s/
