# Cybersecurity Career Roadmap & Portfolio Guide

Panduan ringkas untuk sertifikasi **CySA+, CISA, CRISC** dan pembangunan **Portofolio SOC Analyst**.

---

## 1. CompTIA CySA+ (CS0-003)
**Fokus:** Analisis Keamanan, Threat Hunting, IR.  
**Target:** Security Analyst, SOC Analyst, Incident Responder.

### 📋 Spesifikasi Ujian
| Fitur | Detail |
| :--- | :--- |
| **Kode** | CS0-003 (v3) |
| **Soal** | Max 85 (MCQ + Performance-based) |
| **Durasi** | 165 Menit |
| **Skor Lulus** | 750 (Skala 100-900) |
| **Syarat** | Network+, Security+, 4 thn pengalaman (Disarankan) |

### 🧠 Domain & Bobot
1. **Security Operations (33%)**: Log analysis, SIEM, Threat hunting.
2. **Vulnerability Management (30%)**: Scanning, CVSS, Remediation.
3. **Incident Response (20%)**: Containment, Eradication, Forensics.
4. **Reporting (17%)**: Compliance, Metrics, Communication.

### 📅 Rencana Belajar 6 Minggu
* **M1-2:** Ops & Logs (SIEM, Nmap, Wireshark).
* **M3-4:** Vuln Mgmt (Nessus/OpenVAS, CVSS calc).
* **M5:** IR Frameworks (NIST/SANS) & Reporting.
* **M6:** Practice Exams & PBQ (Performance Based Questions).

---

## 2. ISACA CISA (Certified Information Systems Auditor)
**Fokus:** Audit TI, Kontrol, Assurance.  
**Target:** IT Auditor, Internal Audit, Compliance Officer.

### 📋 Spesifikasi Ujian
| Fitur | Detail |
| :--- | :--- |
| **Versi** | Job Practice 2024 (Efektif 1 Agt 2024) |
| **Soal** | 150 (MCQ) |
| **Durasi** | 240 Menit (4 Jam) |
| **Skor Lulus** | 450 (Skala 200-800) |
| **Syarat** | 5 tahun pengalaman (Waiver avail.) |

### 🧠 Domain & Bobot
1. **Audit Process (18%)**: Risk-based audit, ITAF, Sampling.
2. **IT Governance (18%)**: IT Strategy, Frameworks, Risk Mgmt.
3. **Acquisition & Dev (12%)**: SDLC, Agile, Project Mgmt.
4. **Ops & Resilience (26%)**: ITSM, DR/BCP, Database.
5. **Protection (26%)**: Cyber Security, CIA, Network Sec.

### 📅 Rencana Belajar
* **Tips:** Gunakan *ISACA Review Manual* & *QAE Database*.
* **Fokus:** Pahami "ISACA Mindset" (Auditor tidak memperbaiki, tapi melaporkan).

---

## 3. ISACA CRISC (Risk & Information Systems Control)
**Fokus:** Manajemen Risiko TI & Desain Kontrol.  
**Target:** Risk Manager, ISO, GRC Pro.

### 📋 Spesifikasi Ujian
| Fitur | Detail |
| :--- | :--- |
| **Versi** | Job Practice 2025/2026 |
| **Soal** | 150 (MCQ) |
| **Durasi** | 240 Menit (4 Jam) |
| **Syarat** | 3 tahun pengalaman Risk Mgmt (No Waiver) |

### 🧠 Domain & Bobot
1. **Governance (26%)**: Risk Appetite, Strategy, Culture.
2. **IT Risk Assessment (22%)**: Identify, Analyze, Evaluate (Inherent vs Residual).
3. **Risk Response (32%)**: Mitigate, Transfer, Accept, Avoid + Control Design.
4. **IT & Security (20%)**: Data Lifecycle, Emerging Tech.

---

## 4. SOC Analyst Portfolio (Home Lab)
**Goal:** Membangun lab deteksi serangan & membuat laporan investigasi.

### 🛠️ Lab Setup (Arsitektur)
1. **Victim (Windows 10):**
   - Network: NAT/Host-Only.
   - Disable Defender Real-time Protection.
   - Install **Sysmon** (Config: SwiftOnSecurity).
2. **Attacker (Kali Linux):**
   - Network: Same as Victim.
3. **SIEM (Splunk Free):**
   - Install di Windows/Ubuntu.
   - Ingest: WinEventLog (Security, System, Sysmon).

### ⚔️ Skenario Serangan (Red Team)
Jalankan di Kali Linux / Windows CMD:

**A. Brute Force (RDP/SSH)**
```bash
hydra -l admin -P rockyou.txt rdp://[TARGET_IP]
```

**B. User Backdoor
```cmd
net user hacker P@ssw0rd /add
net localgroup administrators hacker /add
```

**C. Obfuscated PowerShell
```powershell
powershell -e ZWNobyAiSGFja2VkIg==
```

###🛡️Deteksi & Analisis (Blue Team)

Query SPL (Splunk) untuk investigasi:
**A. Detect Brute Force
```splunk
index=* EventCode=4625 | stats count by SourceNetworkAddress | where count > 10
```

**B. Detect New User
```splunk
index=* EventCode=4720 | table _time, TargetUserName, SubjectUserName
```

**C. Detect PowerShell Obfuscation
```splunk
index=* source="*sysmon*" EventCode=1 Image="*powershell.exe*" | regex CommandLine=".*[A-Za-z0-9+/]{20,}=*"
```

