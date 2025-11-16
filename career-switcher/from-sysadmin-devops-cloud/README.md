# 🛡️ Career Switch Guide: **System Administrator / DevOps / Cloud Engineer → Cybersecurity**

Panduan lengkap untuk profesional **SysAdmin, DevOps, dan Cloud Engineer** yang ingin beralih ke dunia **Cybersecurity**, terutama menuju role-role seperti Cloud Security Engineer, Security Engineer (Infrastructure), IAM Engineer, DevSecOps, dan Endpoint/Platform Security.

---

# 1. Kenapa SysAdmin / DevOps / Cloud Sangat Cocok Masuk Cybersecurity?
Skill yang sudah dimiliki sangat relevan:

- Paham infra (server, storage, virtualization)
- Paham automation & CI/CD (DevOps)
- Paham cloud architecture (VPC, SG, IAM)
- Paham systems hardening
- Paham scripting (Bash, PowerShell, Python)
- Paham monitoring & logging

Ini langsung relevan dengan area security seperti:

- Infra & platform security
- Cloud security engineering
- DevSecOps
- IAM & Zero Trust
- Detection engineering

---

# 2. Role Target yang Paling Cocok

| Role | Level | Fokus Utama |
|------|--------|-------------|
| **Cloud Security Engineer** | Mid | Secure AWS/Azure/GCP infra |
| **Security Engineer (Infra/Platform)** | Mid | Hardening, secure configuration |
| **DevSecOps Engineer** | Mid | CI/CD security, SAST/DAST, pipeline hardening |
| **IAM Engineer** | Mid | Identity, access, policies, SSO |
| **Endpoint Security Engineer** | Mid | EDR, hardening, configuration |
| **Detection Engineer** | Mid | SIEM rules, detection logic |
| **Incident Response Engineer** | Mid | IR automation, cloud IR |

---

# 3. Roadmap Skill Development

## Step 1 — Strengthen System & Platform Security
Pelajari:

- OS Hardening (Windows/Linux)
- File integrity monitoring
- Patch & config management
- Sysmon / auditd logging
- Secure system baselines (CIS Benchmarks)

**Resources:**
- CIS Benchmarks: https://www.cisecurity.org/cis-benchmarks
- Microsoft Security Baselines: https://learn.microsoft.com/en-us/windows/security
- Linux Hardening Guide: https://www.stigviewer.com

---

## Step 2 — Cloud Security Fundamentals
Fokus pada 3 cloud utama:

- IAM & Permissions  
- Networking security (SG, NACL, VPC)  
- Key Management (KMS)  
- Logging (CloudTrail, Monitor, Stackdriver)  
- Security Hub / Defender / Security Command Center  

**Resources:**
- AWS Security Hub: https://aws.amazon.com/security
- Azure Security: https://learn.microsoft.com/en-us/azure/security
- GCP Security: https://cloud.google.com/security

---

## Step 3 — DevSecOps & Automation Security
Pelajari:

- CI/CD Security (GitHub Actions, GitLab, Jenkins)
- SAST/DAST scanning
- Secrets management (Vault, KMS, SSM)
- Container security (Docker, Kubernetes)

**Tools:**
- Trivy
- Grype
- Snyk
- OPA / Kyverno
- Falco (runtime security)

---

## Step 4 — Logging, Monitoring, & Detection Engineering
Tools:

- SIEM (Splunk, Sentinel, Elastic)
- Sysmon + Winlogbeat
- Cloud logs (CloudTrail, Azure Monitor)
- Security Onion / Wazuh

Focus skill:

- Query writing (KQL, Lucene)
- Detection rules (Sigma)
- Alert tuning
- MITRE ATT&CK mapping

---

## Step 5 — Identity & Access Management
Pelajari:

- IAM roles, policies, permissions boundaries
- SSO, OAuth, SAML, OIDC
- Zero Trust identity model
- Privileged Access Management (PAM)

**Resources:**
- Okta Docs: https://developer.okta.com  
- Auth0 Docs: https://auth0.com/docs  

---

# 4. Home Lab Guide (Praktis)

## A. Cloud Security Lab (AWS/Azure/GCP)
Setup:

- 1 public subnet, 1 private subnet
- Misconfigured IAM user
- Weak SG rules
- S3/Blob Storage misconfig

Praktik:

- Exploit → Fix misconfig
- Enable CloudTrail/Monitor logs
- Write detection queries

---

## B. DevSecOps Pipeline Lab
Gunakan:

- GitHub Actions  
- Trivy scanning  
- SAST + dependencies scanning  

Goals:

- Build secure CI/CD pipeline
- Integrate secrets scanning
- Implement IaC security (tfsec, checkov)

---

## C. Linux & Windows Hardening Lab
Tasks:

- Deploy Sysmon / auditd
- Analyze logs
- Implement CIS hardening
- Create baseline config

---

# 5. Portfolio Project Ideas

## Entry Level
- Cloud misconfiguration detection & remediation report
- Sysmon/auditd log analysis project
- Hardened Linux + Windows baseline project
- Basic CI/CD security pipeline

## Mid Level
- Create Sigma detection rules  
- Build custom dashboards (KQL/Elastic)  
- End-to-end secure cloud architecture  
- Terraform + security scanning (Checkov/tfsec)  

## Advanced
- Kubernetes runtime detection with Falco  
- Build threat detection pipeline for cloud logs  
- Implement Zero Trust guide  

---

# 6. Tools to Master

## Infrastructure Security
- Sysmon  
- auditd  
- CIS Benchmarking tools  

## Cloud Security
- AWS KMS, IAM, CloudTrail  
- Azure Defender + Sentinel  
- GCP SCC  

## DevSecOps
- Trivy  
- Snyk  
- GitHub Actions security  
- Checkov, tfsec  

## Monitoring / SIEM
- Splunk  
- Wazuh  
- Elastic Stack  
- Microsoft Sentinel  

---

# 7. Certifications

| Sertifikasi | Level | Value |
|-------------|--------|--------|
| **AZ-500** | Mid | Azure security engineer |
| **AWS Security Specialty** | Mid | Cloud security expert |
| **GCP Professional Cloud Security Engineer** | Mid | Google cloud security |
| **CompTIA Security+** | Entry | Solid foundation |
| **CySA+** | Mid | Detection & response |
| **Terraform Associate** | Mid | Infrastructure as code |
| **CKS (Kubernetes Security)** | Advanced | K8s security |

---

# 8. Learning Plan (6 Bulan)

### Month 1–2
- System hardening  
- Logging & monitoring  
- IAM fundamentals  

### Month 3
- Cloud security fundamentals (AWS/Azure/GCP)

### Month 4
- DevSecOps pipeline  
- IaC security  

### Month 5
- SIEM & detection engineering  
- Build 3 portfolio projects  

### Month 6
- Certification preparation  
- Apply roles  

---

# 9. Reference URL (Lengkap)

## Hardening & System Security
- CIS Benchmarks — https://www.cisecurity.org/cis-benchmarks  
- STIGs — https://www.stigviewer.com  

## Cloud Security
- AWS Security — https://aws.amazon.com/security  
- Azure Security — https://learn.microsoft.com/en-us/azure/security  
- GCP Security — https://cloud.google.com/security  

## DevSecOps
- Trivy — https://aquasecurity.github.io/trivy  
- Grype — https://github.com/anchore/grype  
- Checkov — https://www.checkov.io  
- GitHub Actions — https://docs.github.com/actions  

## Detection Engineering
- Sigma Rules — https://github.com/SigmaHQ/sigma  
- Elastic Security — https://www.elastic.co/security  
- Wazuh — https://documentation.wazuh.com  

## Training
- TryHackMe — https://tryhackme.com  
- HTB Academy — https://academy.hackthebox.com  
- INE Cybersecurity — https://ine.com  
