# 🛡️ Career Switch Guide: **Software Developer → Cybersecurity (AppSec / DevSecOps / Security Engineering)**

Panduan lengkap untuk software developer yang ingin beralih ke dunia **Cybersecurity**, khususnya ke area **Application Security (AppSec)**, **DevSecOps**, **Secure Software Engineering**, **Cloud Security**, dan **Security Automation**.

---

# 1. Kenapa Software Developer Sangat Cocok Masuk Cybersecurity?
Developer memiliki keunggulan besar:

- Paham software lifecycle (SDLC)
- Paham code behavior & architecture
- Paham API, database, backend/frontend
- Paham automation & CI/CD
- Terbiasa debugging & tracing issues
- Paham cloud-native apps
- Familiar dengan Git & version control

Skill ini adalah **fondasi AppSec & DevSecOps**.

---

# 2. Role Target yang Paling Cocok

| Role | Level | Fokus Utama |
|------|--------|-------------|
| **Application Security Engineer (AppSec)** | Mid | Secure code review, threat modeling, SAST/DAST |
| **DevSecOps Engineer** | Mid | CI/CD security, dependency scanning, IaC security |
| **Security Automation Engineer** | Mid | Security tooling, scripting, integration |
| **Cloud Security Engineer** | Mid | Secure cloud apps, serverless, API security |
| **Product Security Engineer** | Mid | Secure design, architecture review |
| **Bug Bounty Researcher** | Any | Web security & exploitation |
| **Secure Code Reviewer** | Mid | Code auditing for security defects |
| **Threat Modeling Engineer** | Mid | STRIDE, misuse cases, architecture threat analysis |

---

# 3. Roadmap Skill Development

## Step 1 — Strengthen Security Foundations
Pelajari:

- CIA Triad, OWASP Top 10
- Secure SDLC
- Threat modeling (STRIDE, PASTA)
- Authentication & authorization basics
- API security fundamentals

**Resources:**
- OWASP Top 10: https://owasp.org/www-project-top-ten/
- SANS AppSec: https://www.sans.org/cyber-security-skills-roadmap/
- PortSwigger Academy: https://portswigger.net/web-security

---

## Step 2 — Web & Application Security
Pelajari konsep:

- SQL Injection
- XSS
- CSRF
- SSRF
- IDOR
- JWT attacks
- Session attacks
- API security (REST & GraphQL)
- Authentication flaws
- Secure password storage

**Resources:**
- PortSwigger Academy (BEST): https://portswigger.net/web-security
- OWASP Cheatsheets: https://cheatsheetseries.owasp.org
- HackTricks: https://book.hacktricks.xyz

---

## Step 3 — Secure Coding Practices
Fokus pada:

- Input validation
- Output encoding
- Error handling
- Secrets management
- Dependency security (SCA)
- Secure cryptography usage
- Safe file handling

**Tools:**
- Semgrep
- Snyk
- SonarQube
- Bandit
- Trivy

---

## Step 4 — DevSecOps Pipeline & Automation
Belajar:

- SAST/DAST/SCA scanning
- IaC Security (Terraform, K8s)
- Secure CI/CD (GitHub Actions, GitLab)
- Supply chain security (SBOM, Sigstore)
- Secret scanning

**Tools:**
- Trivy
- Grype
- Checkov
- GitLeaks
- OPA / Kyverno

---

## Step 5 — Cloud Security (Pentig untuk AppSec Modern)
Fokus pada:

- Serverless security
- API Gateway security
- WAF & rate limiting
- Container security
- Runtime detection (Falco)
- IAM permissions for apps

---

## Step 6 — Threat Modeling & Architecture Review
Pelajari:

- STRIDE
- DREAD
- PASTA
- Data flow diagrams (DFD)
- Securing microservices
- Securing monoliths vs distributed systems

---

# 4. Tools to Master

## Application Security Tools
- Burp Suite
- Zap Proxy
- Semgrep
- Snyk
- Trivy
- SonarQube

## DevSecOps Tools
- Jenkins / GitHub Actions / GitLab
- Trivy / Snyk / Grype
- OPA / Kyverno
- Checkov / tfsec

## Cloud & Container Tools
- Docker / Kubernetes
- Falco
- AWS/Azure/GCP security services

## Logging & Monitoring
- Elastic Stack
- CloudTrail
- KMS audit logs

---

# 5. Home Lab Guide (Praktis)

## A. Web App Security Lab
Gunakan:
- Damn Vulnerable Web App (DVWA)
- Juice Shop
- WebGoat (OWASP)

Praktik:
- SQLi
- XSS
- SSRF
- IDOR
- Authentication bypass

---

## B. Secure Coding Lab
Tasks:
- Fix insecure code
- Implement secure authentication
- Replace insecure crypto
- Patch vulnerable dependencies

---

## C. DevSecOps Pipeline Lab
Gunakan:
- GitHub Actions
- Trivy scanning
- Semgrep rules
- IaC scanning (Checkov)

Goals:
- Build security stage in CI/CD
- Auto-block PR with vulnerabilities
- Implement secret-scanning

---

# 6. Portfolio Project Ideas

## Entry Level
- OWASP Juice Shop write-up
- Secure code refactoring examples
- Semgrep rule pack for your language
- CI/CD pipeline with security scanning

## Intermediate
- Threat model for a real architecture
- Container security lab with Falco
- Build SBOM generator for projects

## Advanced
- Write custom SAST rules
- Build secure-by-default CI/CD template
- Architect secure cloud-native application

---

# 7. Certification Path

| Sertifikasi | Level | Value |
|-------------|--------|--------|
| **eJPT** | Entry | Foundation exploitation & security |
| **Security+** | Entry | General security |
| **AWS/Azure/GCP Security** | Mid | Cloud AppSec |
| **GWAPT (SANS)** | Advanced | Web application security gold standard |
| **OSWE (OffSec)** | Expert | Advanced AppSec & code review |
| **Crumble: AppSec Path** | Entry/Mid | Developer-focused |

---

# 8. Learning Plan (6 Bulan)

### Month 1–2
- OWASP Top 10
- Basic exploit labs
- Secure coding practice

### Month 3
- DevSecOps pipeline
- SAST/SCA scanning

### Month 4
- Cloud security fundamentals
- API security deep dive

### Month 5
- Portfolio projects (3–5 projects)
- Threat modeling

### Month 6
- Certification
- Start applying

---

# 9. Reference URL (Lengkap)

## AppSec & Web Security
- OWASP Top 10 — https://owasp.org/www-project-top-ten  
- OWASP Cheatsheets — https://cheatsheetseries.owasp.org  
- PortSwigger Academy — https://portswigger.net/web-security  
- HackerOne Docs — https://docs.hackerone.com  
- HackTricks — https://book.hacktricks.xyz  

## DevSecOps
- Trivy — https://aquasecurity.github.io/trivy  
- Checkov — https://www.checkov.io  
- GitLeaks — https://github.com/gitleaks/gitleaks  
- Snyk — https://snyk.io  

## Secure Coding
- OWASP ASVS — https://owasp.org/www-project-application-security-verification-standard  
- Secure Coding Guides — https://www.veracode.com/security/secure-coding  

## Cloud Security
- AWS Security — https://aws.amazon.com/security  
- Azure Security — https://learn.microsoft.com/en-us/azure/security  
- GCP Security — https://cloud.google.com/security  

## Training
- PortSwigger Academy — https://portswigger.net/web-security  
- HackTheBox Academy — https://academy.hackthebox.com  
- TryHackMe Web Path — https://tryhackme.com/paths  
