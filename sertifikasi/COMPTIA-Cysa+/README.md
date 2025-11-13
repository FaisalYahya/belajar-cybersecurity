# comptia-cysa-plus

Panduan **CompTIA CySA+ (CS0-003, V3)** untuk calon dan pemegang sertifikat.  
Fokus pada format ujian, domain, dan pemeliharaan sertifikasi.

> [!TIP]
> Selaraskan belajar dengan **Exam Objectives** resmi.  
> Prioritaskan domain berbobot tinggi.

## Daftar Isi
- [Ringkasan CySA+](#ringkasan-cysa)
- [Format ujian & bahasa](#format-ujian--bahasa)
- [Domain & bobot ujian](#domain--bobot-ujian)
- [Apa yang dipelajari per domain](#apa-yang-dipelajari-per-domain)
- [Rencana belajar 6 minggu](#rencana-belajar-6-minggu)
- [Pendaftaran, jadwal, dan kebijakan](#pendaftaran-jadwal-dan-kebijakan)
- [Setelah lulus: CEU & biaya CE](#setelah-lulus-ceu--biaya-ce)
- [Latihan cepat](#latihan-cepat)
- [Checklist ringkas](#checklist-ringkas)
- [Referensi resmi](#referensi-resmi)
- [Kontribusi](#kontribusi)

---

## Ringkasan CySA+
CySA+ memvalidasi keterampilan **analisis keamanan** tingkat menengah.  
Direkomendasikan: Network+, Security+, dan **≥4 tahun** pengalaman IR/SOC.  
Ikhtisar & syarat: <https://www.comptia.org/en-us/certifications/cybersecurity-analyst/>

---

## Format ujian & bahasa
Detail resmi: <https://www.comptia.org/en-us/certifications/cybersecurity-analyst/>

- Seri ujian: **CS0‑003 (V3)**.  
- Tanggal rilis: **6 Juni 2023**.  
- Jumlah soal: **maksimum 85** (MCQ + performance‑based).  
- Durasi: **165 menit**.  
- Skor lulus: **750** (skala **100–900**).  
- Bahasa: **English, Japanese, Portuguese, Spanish**.  
- Rekomendasi pengalaman: **IR/SOC ≥4 tahun**.

---

## Domain & bobot ujian
Sesuai **Exam Objectives (PDF)**:  
<https://comptiacdn.azureedge.net/webcontent/docs/default-source/exam-objectives/comptia-cysa-cs0-003-exam-objectives-(1-0)-(2)-(002).pdf>

1. **Security Operations** — **33%**  
2. **Vulnerability Management** — **30%**  
3. **Incident Response Management** — **20%**  
4. **Reporting and Communication** — **17%**

---

## Apa yang dipelajari per domain
**1) Security Operations**  
Arsitektur sistem/jaringan, log ingestion, SIEM, anomali host/jaringan/aplikasi,  
TI & hunting, orkestrasi, automasi, *single pane of glass*.

**2) Vulnerability Management**  
Asset discovery, scanning (agent/agentless, credentialed), hasil alat, CVSS,  
validasi temuan, mitigasi, patch/config management, *exceptions*.

**3) Incident Response Management**  
Framework: Kill Chain, Diamond, ATT&CK.  
Tahap IR: deteksi, analisis, containment, eradication, recovery.  
IR plan, playbook, TTX, forensik, RCA, BC/DR.

**4) Reporting and Communication**  
Laporan compliance & action plan, inhibitor remediasi, metrik/KPI,  
komunikasi pemangku kepentingan, deklarasi insiden, *lessons learned*.

> Detail butir lengkap ada di **Exam Objectives (PDF)**.  
> <https://comptiacdn.azureedge.net/webcontent/docs/default-source/exam-objectives/comptia-cysa-cs0-003-exam-objectives-(1-0)-(2)-(002).pdf>

---

## Rencana belajar 6 minggu
**M1 — Security Operations**  
Baca objectives end‑to‑end. Ringkas log, SIEM, anomali umum.

**M2 — Vulnerability Management**  
Latih discovery & scanning. Prioritaskan CVSS, validasi, dan mitigasi.

**M3 — Incident Response**  
Pelajari framework & siklus IR. Tulis playbook singkat.

**M4 — Reporting & Metrics**  
Bangun template laporan. Tetapkan KPI & alur eskalasi.

**M5 — Praktik alat**  
Hands‑on SIEM (Elastic/Splunk), Wireshark, *scripting* Python/PowerShell.

**M6 — Review & simulasi**  
Dua simulasi **165 menit**. *Gap‑fix* dan istirahat.

---

## Pendaftaran, jadwal, dan kebijakan
- **Jadwalkan ujian** (test center **atau** online/OnVUE):  
  <https://www.comptia.org/en-us/resources/schedule-exam/>  
  <https://www.pearsonvue.com/us/en/comptia.html>
- **Kebijakan retake** (gagal pertama bisa retake segera; percobaan ≥3 **tunggu 14 hari**):  
  <https://help.comptia.org/hc/en-us/articles/13455025507860-What-Are-the-Exam-Retake-Policies-for-Client-Proctored-Exams>

> [!NOTE]
> Harga voucher bervariasi per wilayah & promo.  
> Cek langsung di **CompTIA Store**.

---

## Setelah lulus: CEU & biaya CE
- **Kebutuhan renewal**: **60 CEUs** tiap **3 tahun** (CySA+ V3).  
  <https://www.comptia.org/en-us/resources/ce/renew-options/renewing-cysa-single/>  
- **Biaya CE**: total **US$150/3 tahun** untuk CySA+.  
  <https://help.comptia.org/hc/en-us/articles/14382051258004-What-Are-the-Fees-to-Renew-My-Certification>  
- **Tanpa biaya CE** bila memilih salah satu opsi ini:  
  **Lulus versi ujian terbaru** atau **meraih sertifikasi CompTIA tingkat lebih tinggi**.  
  <https://www.comptia.org/en-us/resources/ce/choose/renew-with-a-single-activity/pass-the-latest-release-of-your-comptia-exam/>  
  <https://www.comptia.org/en-us/resources/ce/choose/renew-with-a-single-activity/earn-a-higher-level-comptia-certification/>  
- **CE Tokens** tersedia bila perlu.  
  <https://www.comptia.org/en-us/resources/ce/learn/continuing-education-renewal-fees/>

---

## Latihan cepat
- Bangun *playbook* IR untuk ransomware.  
- Jalankan vuln scan terjadwal dan nilai CVSS.  
- Tulis laporan eksekutif 1 halaman dengan KPI.  
- Tangkap & analisis *pcap* anomali DNS/HTTP.  
- Buat *dashboard* SIEM sederhana untuk auth & egress.

---

## Checklist ringkas
- [ ] Menguasai domain & bobot CS0‑003.  
- [ ] Dua simulasi **165 menit** selesai.  
- [ ] Playbook IR dan template laporan siap.  
- [ ] Jadwal ujian via CompTIA/Pearson VUE.  
- [ ] Pahami kebijakan retake & masa voucher.  
- [ ] Rencana **CEU 60/3 tahun** + opsi tanpa biaya CE.

---

## Referensi resmi
- CySA+ overview & exam details: <https://www.comptia.org/en-us/certifications/cybersecurity-analyst/>  
- Exam Objectives (PDF): <https://comptiacdn.azureedge.net/webcontent/docs/default-source/exam-objectives/comptia-cysa-cs0-003-exam-objectives-(1-0)-(2)-(002).pdf>  
- Schedule exam: <https://www.comptia.org/en-us/resources/schedule-exam/>  
- Pearson VUE CompTIA: <https://www.pearsonvue.com/us/en/comptia.html>  
- Retake policy: <https://help.comptia.org/hc/en-us/articles/13455025507860-What-Are-the-Exam-Retake-Policies-for-Client-Proctored-Exams>  
- Renewing CySA+ (single): <https://www.comptia.org/en-us/resources/ce/renew-options/renewing-cysa-single/>  
- CE fees (total per siklus): <https://help.comptia.org/hc/en-us/articles/14382051258004-What-Are-the-Fees-to-Renew-My-Certification>  
- Renew with latest exam (CE fee **di‑waive**): <https://www.comptia.org/en-us/resources/ce/choose/renew-with-a-single-activity/pass-the-latest-release-of-your-comptia-exam/>  
- Earn a higher-level CompTIA certification: <https://www.comptia.org/en-us/resources/ce/choose/renew-with-a-single-activity/earn-a-higher-level-comptia-certification/>  
- CE tokens & pembayaran: <https://www.comptia.org/en-us/resources/ce/learn/continuing-education-renewal-fees/>

---

## Kontribusi
- Fork repository ini.  
- Buat branch fitur terpisah.  
- Gunakan commit message yang jelas.  
- Ajukan pull request ringkas.

---

[⬆️ Kembali ke atas](#comptia-cysa-plus)
