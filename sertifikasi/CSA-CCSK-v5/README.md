# Roadmap Belajar & Lulus Cloud Security Alliance CCSK v5

> **Bahasa:** Indonesia
> **Level:** Beginner (tanpa pengalaman cloud security)
> **Tujuan:** Lulus ujian **Certificate of Cloud Security Knowledge (CCSK) v5** dari Cloud Security Alliance

---

## Daftar Isi

* [1. Gambaran Singkat CCSK v5](#1-gambaran-singkat-ccsk-v5)
* [2. Profil Pembaca & Prasyarat](#2-profil-pembaca--prasyarat)
* [3. Cara Menggunakan Roadmap Ini](#3-cara-menggunakan-roadmap-ini)
* [4. Ringkasan Domain & Bobot Ujian](#4-ringkasan-domain--bobot-ujian)
* [5. Strategi Belajar Tingkat Tinggi](#5-strategi-belajar-tingkat-tinggi)
* [6. Roadmap 8 Minggu](#6-roadmap-8-minggu)
* [7. Checklist Harian & Mingguan](#7-checklist-harian--mingguan)
* [8. Sumber Belajar Utama](#8-sumber-belajar-utama)
* [9. Tips Saat Ujian](#9-tips-saat-ujian)
* [10. FAQ Mini](#10-faq-mini)

---

## 1. Gambaran Singkat CCSK v5

**CCSK (Certificate of Cloud Security Knowledge)** adalah sertifikasi **vendor-neutral** dari Cloud Security Alliance (CSA) yang menguji pemahaman dasar–menengah tentang konsep dan best practice keamanan cloud, termasuk Zero Trust, DevSecOps, cloud telemetry, dan artificial intelligence.([Cloud Security Alliance][1])

Hal penting tentang ujian **CCSK v5**:

* Format:

  * 60 soal **multiple-choice**
  * Waktu: **120 menit**
  * Mode: **online, open-book**, non‑proctored (tidak diawasi)([CSA Exams][2])
* Passing score: **80%** (minimal 48 soal benar dari 60)([QA][3])
* Token ujian:

  * Harga: sekitar **US$445** termasuk **2 kali attempt**([CSA Exams][4])
  * Token berlaku **2 tahun** sejak pembelian([CSA Exams][2])
* Bahasa ujian: saat ini **Inggris**([QA][3])
* Sertifikat **tidak kadaluarsa** (lifetime), namun terkait ke **versi** tertentu (v5, v4, dst). CSA merekomendasikan tetap update dengan versi terbaru.([CSA Exams][4])

**Level:** CCSK secara umum diposisikan sebagai **entry‑level/basics cloud security** dan sering dijadikan pondasi sebelum sertifikasi seperti CCSP.([Reddit][5])

---

## 2. Profil Pembaca & Prasyarat

Roadmap ini didesain untuk:

* Pengguna **pemula** yang:

  * Belum pernah bekerja di cloud / cloud security
  * Belum punya sertifikasi keamanan informasi lain
* Tapi:

  * Nyaman menggunakan komputer
  * Tidak alergi dengan teks berbahasa Inggris 😄

**Tidak ada prasyarat resmi** berupa pengalaman kerja atau sertifikasi lain untuk mengikuti CCSK. Anda cukup:

1. Belajar (self‑study / training)
2. Membuat akun di platform CSA Exams
3. Membeli token dan mengambil ujian([CSA Exams][4])

Skill dasar yang **sangat membantu**:

* Konsep IT dasar (server, aplikasi, database, jaringan)
* Dasar **networking** (IP, subnet, firewall, VPN—level sangat high‑level saja)
* Dasar **security** (confidentiality, integrity, availability, access control)

Kalau Anda benar‑benar **fresh** dari non‑IT, roadmap ini tetap bisa dipakai, tapi tambahkan:

* ±2–4 minggu sebelum **Minggu 1** untuk belajar:

  * Dasar cloud (AWS/Azure/GCP intro)
  * Dasar jaringan & OS (banyak kursus gratis di YouTube / MOOC)

---

## 3. Cara Menggunakan Roadmap Ini

* **Durasi rekomendasi:** ± **8 minggu**
* **Intensitas:** 1–2 jam per hari, 5–6 hari per minggu
* Fokus utama:

  1. Kuasai **Study Guide CCSK v5**
  2. Latihan menjawab soal mirip ujian
  3. Pahami konsep, jangan sekadar hafalan / mencari teks saat ujian

Kapan membeli token?

* Ideal: setelah melewati **Minggu 3–4**, ketika sudah yakin akan menyelesaikan roadmap.
* Ingat token berlaku 2 tahun, jadi Anda punya ruang waktu yang luas.([CSA Exams][2])

---

## 4. Ringkasan Domain & Bobot Ujian

Ujian CCSK v5 mencakup **12 domain** utama. **Jumlah soal per domain** menurut CCSK v5 FAQ:

| #  | Domain                                   | # Soal | Catatan singkat                                                       |
| -- | ---------------------------------------- | :----: | --------------------------------------------------------------------- |
| 1  | Cloud Computing Concepts & Architectures |    5   | Konsep dasar cloud, model layanan, arsitektur, shared responsibility  |
| 2  | Cloud Governance                         |    5   | Kebijakan, struktur tata kelola, roles, decision-making               |
| 3  | Risk, Audit & Compliance                 |    5   | Manajemen risiko, compliance frameworks, audit di cloud               |
| 4  | Organization Management                  |    5   | Struktur organisasi, people, proses, program keamanan cloud           |
| 5  | Identity & Access Management             |    4   | IAM, authN/authZ, federation, least privilege                         |
| 6  | Security Monitoring                      |    4   | Logging, telemetry, SIEM, deteksi & respon                            |
| 7  | Infrastructure & Networking              |    6   | Network segmentation, security groups, firewalls, hybrid connectivity |
| 8  | Cloud Workload Security                  |    7   | VM/container/security controls di level compute                       |
| 9  | Data Security                            |    5   | Klasifikasi data, enkripsi, key management, DLP                       |
| 10 | Application Security                     |    6   | SDLC, DevSecOps, CI/CD, testing, API security                         |
| 11 | Incident Response & Resilience           |    5   | IR plan, BCP/DR, resilience pattern                                   |
| 12 | Related Technologies & Strategies        |    3   | Zero Trust, AI/GenAI, data lakes, teknologi pendukung lainnya         |

Total: 60 soal. Domain dengan **soal terbanyak**: 7, 8, 10 (infrastruktur, workload, aplikasi).

---

## 5. Strategi Belajar Tingkat Tinggi

### 5.1. Fokus Utama: Study Guide & Prep Kit

Body of knowledge CCSK v5 **dikondensasi dalam CCSK v5 Study Guide**, yang disediakan gratis dalam **CCSK v5 Prep Kit**.([CSA Exams][4])

> Untuk ujian, **Study Guide adalah sumber nomor 1**.
> Security Guidance v5 memberikan kedalaman tambahan, tapi tidak wajib dikuasai penuh untuk lulus.

Prioritas sumber:

1. **CCSK v5 Study Guide** (wajib)
2. **Sample questions**/contoh soal dari Prep Kit (wajib)
3. **Security Guidance v5** (opsional: baca bagian yang sulit)
4. **Cloud Controls Matrix (CCM)** – pahami konsep, bukan hafalan butir per butir([Cloud Security Alliance][6])

### 5.2. Hindari “jebakan open-book”

Walau **open-book**, CSA sendiri menekankan: karena soal cukup panjang dan waktu terbatas, jangan terlalu bergantung pada mencari teks saat ujian.([CSA Exams][2])

Artinya:

* Anggap ujian **closed-book** saat belajar
* Gunakan dokumen hanya sebagai **referensi cepat**:

  * Cek istilah
  * Cek diagram / definisi spesifik

### 5.3. Pola Belajar yang Direkomendasikan

Setiap domain:

1. **Baca**: Study Guide untuk domain tersebut (1–2 kali)
2. **Catat**: mind map / bullet notes (istilah penting, diagram)
3. **Hubungkan dengan dunia nyata**:

   * Bayangkan organisasi sederhana: startup / kantor Anda
   * Aplikasikan konsep ke skenario itu
4. **Latihan soal**:

   * Pakai sample questions CSA dulu
   * Tambahan: bank soal lain, tapi hati‑hati dengan sumber tidak resmi
5. **Review**:

   * Cek domain mana yang paling lemah berdasarkan hasil latihan

---

## 6. Roadmap 8 Minggu

Tabel ringkas:

| Fase | Minggu | Fokus Utama                                  |
| ---- | ------ | -------------------------------------------- |
| 0    | 0      | Setup & orientasi                            |
| 1    | 1      | Fondasi cloud & Domain 1                     |
| 2    | 2      | Governance, Risk & Org (Domain 2–4)          |
| 3    | 3–4    | Infra, Network, IAM, Monitoring (Domain 5–7) |
| 4    | 5–6    | Workload, Data, App (Domain 8–10)            |
| 5    | 7      | IR, Resilience, Strategi (Domain 11–12)      |
| 6    | 8      | Final review & ujian                         |

### Fase 0 – Setup (Hari 1–2)

* [ ] Buat akun di platform **CSA Exams**
* [ ] Download **CCSK v5 Prep Kit** (Study Guide, FAQ, Sample Questions)
* [ ] Buat folder khusus (fisik/digital) untuk:

  * PDF Study Guide
  * Catatan per domain
  * Link penting
* [ ] Tentukan target:

  * Tanggal ujian tentatif (sekitar akhir Minggu 8)
  * Jam belajar harian (misalnya 20.00–21.30)

> Opsional: sudah boleh membeli token ujian di fase ini, tapi tidak wajib.

---

### Fase 1 – Fondasi Cloud (Minggu 1)

**Tujuan minggu ini:**

* Paham konsep dasar cloud & arsitektur high-level (Domain 1)
* Jika sangat pemula cloud: mengejar *basic cloud computing*

**Minggu 1 – To‑do**

* [ ] Baca **Study Guide – Domain 1: Cloud Computing Concepts & Architectures**
* [ ] Catat:

  * Perbedaan **IaaS, PaaS, SaaS**
  * Model deployment: **Public / Private / Hybrid / Community**
  * Konsep **multi-tenancy, elasticity, resource pooling**
  * Model **shared responsibility**
* [ ] (Opsional) tonton video pengantar cloud (AWS/Azure/GCP intro)
* [ ] Latihan:

  * [ ] Buat 5–10 contoh layanan populer dan kategorikan (IaaS/PaaS/SaaS)
  * [ ] Jawab sample question yang terkait Domain 1

---

### Fase 2 – Governance, Risk & Organization (Minggu 2)

**Fokus domain:**

* Domain 2 – Cloud Governance
* Domain 3 – Risk, Audit & Compliance
* Domain 4 – Organization Management

**Minggu 2 – To‑do**

* [ ] Baca Study Guide Domain 2–4 satu per satu
* [ ] Pahami:

  * Peran dan tanggung jawab:

    * Cloud customer vs provider vs regulator
  * Proses **risk management** di cloud
  * Konsep **policies, standards, procedures, guidelines**
  * High-level compliance: ISO 27001, SOC 2, dsb (cukup konsep saja)
* [ ] Latihan:

  * [ ] Gambar struktur **cloud governance** untuk organisasi fiktif (misalnya startup 50 orang)
  * [ ] Tuliskan minimal 5 risiko khas cloud & kontrol mitigasinya
* [ ] Kerjakan sample questions untuk domain 2–4

---

### Fase 3 – Infrastruktur, Networking, IAM, Monitoring (Minggu 3–4)

**Fokus domain:**

* Domain 5 – Identity & Access Management
* Domain 6 – Security Monitoring
* Domain 7 – Infrastructure & Networking (bobot tinggi)

#### Minggu 3 – IAM & Infrastruktur Dasar

* [ ] Baca Domain 5 & 7 (pertama kali)
* [ ] Pahami:

  * Konsep **identity, account, role**
  * **Authentication vs Authorization**
  * **RBAC, ABAC, least privilege**
  * Network di cloud:

    * Segmen (VPC/VNet concepts), subnet, security group, firewall
    * Hybrid connectivity (VPN, Direct Connect/ExpressRoute high level)
* [ ] Latihan:

  * [ ] Desain akses user sederhana: admin, developer, finance, tamu
  * [ ] Gambar jaringan sederhana: public subnet, private subnet, on‑prem

#### Minggu 4 – Monitoring & Pendalaman Infrastruktur

* [ ] Baca Domain 6 (Security Monitoring) + re‑read Domain 7
* [ ] Pahami:

  * **Logging vs events vs telemetry**
  * SIEM, alerting, use case monitoring umum di cloud
  * Konsep **Zero Trust** terkait network (misalnya micro‑segmentation)
* [ ] Latihan:

  * [ ] Buat daftar log penting (IAM, network, system, app) untuk dipantau
  * [ ] Kerjakan sample questions domain 5–7
* [ ] Akhir Minggu 4:

  * [ ] Lakukan mini‑mock exam 20–30 soal kombinasi domain 1–7
  * [ ] Identifikasi domain paling lemah → tandai untuk revisi

> Di akhir fase ini, Anda sudah punya fondasi kuat di setengah domain ujian.
> Kalau progress oke, **saat inilah waktu yang bagus untuk membeli token ujian** (kalau belum).

---

### Fase 4 – Workload, Data, Application (Minggu 5–6)

**Fokus domain:**

* Domain 8 – Cloud Workload Security (bobot tertinggi: 7 soal)
* Domain 9 – Data Security
* Domain 10 – Application Security (6 soal)

#### Minggu 5 – Workload & Data

* [ ] Baca Domain 8 (Workload Security)

  * VM vs container vs serverless (konsep)
  * Hardening images, patch management, konfigurasi secure
* [ ] Baca Domain 9 (Data Security)

  * Data classification
  * Encryption at rest / in transit
  * Key management (KMS, HSM, key rotation)
* [ ] Latihan:

  * [ ] Buat tabel **tingkat sensitivitas data** + kontrol yang diperlukan
  * [ ] Kerjakan sample questions Domain 8–9

#### Minggu 6 – Application Security & DevSecOps

* [ ] Baca Domain 10 (Application Security)

  * Secure SDLC
  * CI/CD pipeline & DevSecOps
  * Skenario umum: OWASP Top 10 (high-level), API security
* [ ] Latihan:

  * [ ] Gambar pipeline CI/CD sederhana dan label di mana kontrol keamanan ditempatkan
  * [ ] Kerjakan sample questions Domain 10
* [ ] Re‑review:

  * Domain 8–10 sekali lagi dengan fokus ke bagian yang membingungkan

---

### Fase 5 – Incident Response, Resilience & Related Tech (Minggu 7)

**Fokus domain:**

* Domain 11 – Incident Response & Resilience
* Domain 12 – Related Technologies & Strategies (Zero Trust, AI/GenAI, data lakes, dll.)([Cloud Security Alliance][6])

**Minggu 7 – To‑do**

* [ ] Baca Domain 11 & 12
* [ ] Pahami:

  * Siklus **incident response** di cloud
  * Peran provider vs customer saat insiden
  * Business Continuity & Disaster Recovery di cloud
  * Konsep **Zero Trust**, pengaruh ke desain cloud
  * Peran **AI/GenAI**, security analytics, data lake untuk security
* [ ] Latihan:

  * [ ] Tulis skenario insiden sederhana (mis. kebocoran credential) + langkah respon
  * [ ] Kerjakan sample questions Domain 11–12
* [ ] Buat rangkuman **1–2 halaman** seluruh domain (cheat sheet pribadi)

---

### Fase 6 – Final Review & Ujian (Minggu 8)

**Minggu 8 – To‑do**

* [ ] Simulasi ujian:

  * **2x sesi** latihan 60 soal (bisa kombinasi dari berbagai sumber)
  * Atur waktu **120 menit** seolah ujian sungguhan
  * Jangan lihat catatan
* [ ] Analisa hasil:

  * Domain mana yang <80% → fokus revisi
* [ ] Review cepat:

  * Diagram, tabel, dan definisi penting (shared responsibility, encryption, Zero Trust components, dsb.)
* [ ] Siapkan environment ujian:

  * Laptop + charger
  * Koneksi internet stabil
  * Browser & PDF viewer (untuk buka Study Guide)
* [ ] Tentukan hari dan jam ujian (ingat: bisa diambil kapan saja, 24/7)([CSA Exams][2])

Hari H:

* Blok 2,5–3 jam waktu Anda (120 menit ujian + buffer)
* Login ke platform CSA Exams dan mulai ujian
* Setelah selesai, nilai akan **langsung tampil**.([CSA Exams][2])

---

## 7. Checklist Harian & Mingguan

### Checklist Harian (contoh 90 menit)

* [ ] 45–60 menit baca Study Guide / Security Guidance
* [ ] 15–20 menit membuat / merapikan catatan
* [ ] 10–20 menit menjawab 5–10 soal latihan
* [ ] 5 menit review salah jawab & tandai konsep yang belum jelas

### Checklist Mingguan

* [ ] Domain minggu ini dibaca minimal sekali
* [ ] Ada catatan ringkas untuk domain tersebut
* [ ] Minimal 20–30 soal latihan dikerjakan
* [ ] Domain yang masih lemah dicatat untuk review di Minggu 8

---

## 8. Sumber Belajar Utama

> **Catatan:** Link ditulis dalam format `code` agar mudah di‑copy ke browser.

### 8.1. Sumber Resmi (CSA) – Sangat Disarankan

* **CCSK v5 Prep Kit (gratis)** – Study Guide, FAQ, sample questions, curriculum, dll.([Cloud Security Alliance][7])

  * `https://cloudsecurityalliance.org/artifacts/ccsk-v5-prep-kit`
* **Halaman resmi CCSK** (informasi umum sertifikasi)([Cloud Security Alliance][1])

  * `https://cloudsecurityalliance.org/education/ccsk`
* **CSA Exams – CCSK FAQ** (detail ujian, harga token, aturan ujian)([CSA Exams][2])

  * `https://exams.cloudsecurityalliance.org/faq`
* **Security Guidance for Cloud Computing v5** (referensi mendalam 12 domain)([Cloud Security Alliance][6])

  * `https://cloudsecurityalliance.org/artifacts/security-guidance-v5`
* **Cloud Controls Matrix (CCM)** – katalog kontrol keamanan cloud([Cloud Security Alliance][6])

  * `https://cloudsecurityalliance.org/research/cloud-controls-matrix`

### 8.2. Training Opsional (Berbayar)

* **CCSK v5 Foundation / Plus** – training resmi (self‑paced / instructor‑led)([training.cloudsecurityalliance.org][8])

  * `https://training.cloudsecurityalliance.org`
* Training dari partner (Intrinsec, QA, dsb.) – pilih sesuai budget & gaya belajar.

### 8.3. Sumber Tambahan (Umum)

* Video pengantar:

  * Basic cloud computing (AWS / Azure / GCP)
  * Network & security fundamentals
* Buku / artikel:

  * Pengantar **information security** & **risk management**
  * Artikel Zero Trust, DevSecOps, dan incident response di cloud

---

## 9. Tips Saat Ujian

* **Siapkan lingkungan:**

  * Tempat tenang, koneksi stabil, pastikan tidak akan diganggu 2 jam
* **Atur strategi waktu:**

  * 60 soal / 120 menit → ±2 menit per soal
  * Kalau buntu, tandai dan lanjut ke soal berikutnya, kembali di akhir
* **Gunakan open-book dengan cerdas:**

  * Jangan cari jawaban setiap soal
  * Gunakan Study Guide hanya untuk:

    * Istilah yang benar‑benar lupa
    * Tabel/diagram spesifik
* **Baca soal perlahan:**

  * Perhatikan kata kunci seperti *MOST*, *LEAST*, *BEST*, *FIRST*, *EXCEPT*
* **Setelah submit:**

  * Anda akan melihat skor total + skor per domain (tanpa jawaban detail)([CSA Exams][2])
  * Kalau belum lulus, gunakan analisis domain lemah untuk rencana belajar ulang sebelum attempt kedua

---

## 10. FAQ Mini

**Q: Apakah CCSK cocok untuk pemula tanpa pengalaman cloud?**
**A:** Ya. Banyak organisasi & trainer menggunakan CCSK sebagai **pintu masuk** ke cloud security. Tidak ada prasyarat resmi; pemahaman IT & security dasar saja sudah cukup, sisanya bisa dikejar selama belajar.([CSA Exams][4])

---

**Q: Berapa lama idealnya belajar sebelum ujian?**
**A:** Dengan 1–2 jam per hari, 5–6 hari per minggu, **8 minggu** biasanya sudah realistis untuk pemula. Jika sudah punya pengalaman cloud/security, bisa jauh lebih cepat.

---

**Q: Apakah sertifikat CCSK kadaluarsa?**
**A:** Menurut CSA, **sertifikat CCSK tidak kadaluarsa**, tapi Anda dikaitkan dengan versi tertentu (v4 atau v5). Disarankan mengikuti perkembangan versi terbaru agar tetap relevan.([CSA Exams][4])

---

**Q: Setelah CCSK, sebaiknya lanjut ke mana?**
Beberapa jalur populer:

* **CCSP (ISC2)** – sertifikasi cloud security level lebih lanjut (butuh pengalaman kerja)
* Sertifikasi vendor:

  * AWS Security Specialty
  * Azure Security Engineer
  * Google Professional Cloud Security Engineer
* Sertifikasi security umum:

  * Security+, CISSP associate, dsb.


[1]: https://cloudsecurityalliance.org/education/ccsk "Certificate of Cloud Security Knowledge (CCSK) | CSA"
[2]: https://exams.cloudsecurityalliance.org/faq "Frequently Asked Questions - CSA Exams Platform"
[3]: https://www.qa.com/media/uqmbazxf/ccsk-faq.pdf?utm_source=chatgpt.com "CCSK v5 FAQ"
[4]: https://exams.cloudsecurityalliance.org/faq?utm_source=chatgpt.com "Frequently Asked Questions - CSA Exams Platform"
[5]: https://www.reddit.com/r/CCSP/comments/16cew9c/ccsp_and_ccsk/?utm_source=chatgpt.com "CCSP and CCSK : r/CCSP"
[6]: https://cloudsecurityalliance.org/artifacts/security-guidance-v5?utm_source=chatgpt.com "Security Guidance for Cloud Computing v5 | CSA"
[7]: https://cloudsecurityalliance.org/artifacts/ccsk-v5-prep-kit?utm_source=chatgpt.com "CCSK v5 Prep Kit | CSA"
[8]: https://training.cloudsecurityalliance.org/certificate-of-cloud-security-knowledge-v5?utm_source=chatgpt.com "Certificate of Cloud Security Knowledge v5 - CSA Training"
