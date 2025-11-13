# modul-04-pengenalan-security

Dasar **cybersecurity** dan **information security** untuk pemula.  
Fokus pada konsep, peran, dan praktik awal.  
Bahas perbedaan istilah dengan contoh ringkas.

> [!TIP]
> Mulai dari risiko, bukan dari alat.  
> Dokumentasikan keputusan keamanan sejak awal.

## Daftar Isi
- [Tujuan belajar](#tujuan-belajar)
- [Prasyarat](#prasyarat)
- [Definisi inti](#definisi-inti)
- [Perbedaan utama](#perbedaan-utama)
- [Prinsip keamanan](#prinsip-keamanan)
- [Jenis kontrol keamanan](#jenis-kontrol-keamanan)
- [GRC ringkas](#grc-ringkas)
- [Manajemen risiko](#manajemen-risiko)
- [Kerangka kerja populer](#kerangka-kerja-populer)
- [Domain keamanan utama](#domain-keamanan-utama)
- [Incident response dasar](#incident-response-dasar)
- [Threat intel dan ATT&CK](#threat-intel-dan-attck)
- [Security testing dan assurance](#security-testing-dan-assurance)
- [Logging, monitoring, dan deteksi](#logging-monitoring-dan-deteksi)
- [Privasi dan perlindungan data](#privasi-dan-perlindungan-data)
- [Kebijakan, standar, prosedur](#kebijakan-standar-prosedur)
- [Metrik dan pelaporan](#metrik-dan-pelaporan)
- [Template praktis](#template-praktis)
- [Latihan cepat](#latihan-cepat)
- [Checklist ringkas](#checklist-ringkas)
- [Glosarium mini](#glosarium-mini)
- [Referensi lanjutan](#referensi-lanjutan)
- [Kontribusi](#kontribusi)

---

## Tujuan belajar
- Memahami perbedaan cybersecurity dan information security.  
- Mengenali prinsip dan kontrol keamanan inti.  
- Menilai risiko sederhana secara terstruktur.  
- Mengetahui siklus incident response dasar.

## Prasyarat
- Menguasai dasar IT dan jaringan.  
- Mampu memakai Linux dan CLI.  
- Punya repo catatan belajar.

---

## Definisi inti
- **Information security (InfoSec)** melindungi **semua informasi**.  
- Media bisa **digital, fisik, atau manusia**.  
- **Cybersecurity** fokus **teknologi informasi dan jaringan**.  
- Fokus pada **sistem, aplikasi, dan data digital**.  
- Keduanya sangat **overlap**, berbeda pada **cakupan**.

---

## Perbedaan utama
- InfoSec mencakup **kebijakan, fisik, dan manusia**.  
- Cybersecurity menekankan **teknik, alat, dan arsitektur digital**.  
- InfoSec menetapkan **governance dan kebijakan**.  
- Cybersecurity mengeksekusi **kontrol teknis dan operasional**.  
- InfoSec menetapkan **risk appetite** organisasi.  
- Cybersecurity mengelola **ancaman operasional harian**.

> [!NOTE]
> Anggap cybersecurity sebagai **subset praktis** dari InfoSec.  
> Sering diatur oleh kebijakan InfoSec.

---

## Prinsip keamanan
- **CIA triad**: confidentiality, integrity, availability.  
- **Least privilege** untuk akses minimal.  
- **Separation of duties** kurangi penyalahgunaan.  
- **Defense in depth** gunakan kontrol berlapis.  
- **Zero Trust**: verifikasi terus menerus.  
- **Security by design** sejak perancangan awal.  
- **Privacy by design** untuk data pribadi.

---

## Jenis kontrol keamanan
**Berdasarkan tujuan**
- Preventive: mencegah kejadian.  
- Detective: mendeteksi kejadian.  
- Corrective: memulihkan kondisi.

**Berdasarkan sifat**
- Administrative: kebijakan dan proses.  
- Technical: alat dan konfigurasi.  
- Physical: kunci dan akses fisik.

---

## GRC ringkas
- **Governance** menetapkan arah dan kebijakan.  
- **Risk management** menilai dan mengelola risiko.  
- **Compliance** memastikan kepatuhan.  
- Tiga lini pertahanan membantu struktur.  
- Dokumentasi adalah bukti kepatuhan.

---

## Manajemen risiko
- Aset, ancaman, dan vulnerability membentuk risiko.  
- Risiko disederhanakan: **Risk ≈ Likelihood × Impact**.  
- Perlakuan risiko: **avoid, reduce, transfer, accept**.  
- Catat keputusan pada **risk register**.  
- Tinjau risiko secara berkala.

**Contoh penilaian sederhana**
```text
Aset: Database pelanggan
Ancaman: Ransomware
Vulnerability: Patch tertunda
Likelihood: Sedang
Impact: Tinggi
Risk level: Tinggi
Treatment: Percepat patch, backup teruji, EDR aktif
Owner: Head of IT
Due date: 30 hari
````

---

## Kerangka kerja populer

* **NIST CSF** untuk kerangka manajemen keamanan.
* **ISO/IEC 27001** untuk sistem manajemen keamanan.
* **ISO/IEC 27002** untuk kontrol panduan.
* **CIS Controls v8** untuk prioritas praktis.
* **NIST SP 800-53** untuk kontrol komprehensif.
* Pilih sesuai konteks dan regulasi.

---

## Domain keamanan utama

* **Identity Security**: IAM, MFA, SSO, PAM.
* **Endpoint Security**: EPP, EDR, hardening.
* **Network Security**: segmentation, firewall, VPN.
* **Application Security**: SDLC, SAST, DAST, SCA.
* **Data Security**: klasifikasi, DLP, enkripsi.
* **Cloud Security**: shared responsibility, posture.
* **Physical Security**: kontrol akses fisik.

---

## Incident response dasar

* Tahapan: **Prepare, Detect, Analyze**.
* Lanjut: **Contain, Eradicate, Recover**.
* Akhiri dengan **Lessons learned**.
* Gunakan **playbook** untuk konsistensi.
* Latih **tabletop exercise** rutin.

**Contoh playbook ringkas**

```text
Trigger: Alert EDR tingkat tinggi
Triage: Validasi indikator dan konteks
Containment: Isolasi host dari jaringan
Eradication: Hapus payload dan persistence
Recovery: Pulihkan dari backup tepercaya
Review: Tambah deteksi dan perbaikan kontrol
```

---

## Threat intel dan ATT&CK

* **Threat intelligence** memberi konteks ancaman.
* **MITRE ATT&CK** memetakan taktik dan teknik.
* **Kill Chain** membantu alur serangan.
* Korelasikan alert dengan **taktik** relevan.
* Prioritaskan **detection** pada teknik dominan.

---

## Security testing dan assurance

* **Vulnerability scanning** untuk temuan cepat.
* **Penetration testing** untuk validasi risiko.
* **Red teaming** untuk simulasi adversary.
* **SAST/DAST/SCA** untuk aplikasi.
* **Configuration review** untuk baseline sistem.
* Dokumentasikan **scope dan izin**.

---

## Logging, monitoring, dan deteksi

* Kumpulkan log ke **SIEM**.
* Gunakan **use case** dan alert terukur.
* Pantau endpoint dengan **EDR**.
* Pantau jaringan dengan **NDR**.
* Tindak alert dengan **triage standar**.

---

## Privasi dan perlindungan data

* Klasifikasikan data sejak awal.
* Gunakan **encryption at rest** dan **in transit**.
* Terapkan **data minimization** dan **retention**.
* Audit akses data berkala.
* Patuhi regulasi setempat yang relevan.

---

## Kebijakan, standar, prosedur

* **Policy** menyatakan **apa** dan **mengapa**.
* **Standard** menjelaskan **tingkat minimum**.
* **Procedure** menjelaskan **bagaimana**.
* **Guideline** memberi **saran fleksibel**.
* Versi dan kepemilikan harus jelas.

---

## Metrik dan pelaporan

* Gunakan **KPI** untuk kinerja program.
* Gunakan **KRI** untuk indikator risiko.
* Laporkan tren, bukan angka mentah.
* Kaitkan dengan tujuan bisnis.
* Visualisasi membantu keputusan.

---

## Template praktis

**Kebijakan kata sandi (contoh)**

```yaml
policy: Password Policy
scope: All users and systems
requirements:
  - MinLength: 12
  - MFA: required for remote access
  - Reuse: remember 5 passwords
  - Rotation: only on compromise
  - Storage: salted hashing, modern KDF
```

**Klasifikasi data (contoh)**

```yaml
classification:
  - Public: boleh dibagikan
  - Internal: untuk karyawan
  - Confidential: terbatas unit terkait
  - Restricted: sangat terbatas, audit wajib
```

**Pernyataan akses minimal**

```text
Akses diberikan sesuai tugas.
Akses ditinjau tiap tiga bulan.
Akses dicabut saat offboarding.
```

---

## Latihan cepat

* Buat **risk register** minimal lima entri.
* Tulis **password policy** satu halaman.
* Petakan proses bisnis dan aset kritikal.
* Susun **IR playbook** untuk ransomware.
* Buat **data classification** ringkas untuk organisasi fiktif.
* Implementasikan **MFA** pada akun penting.
* Dokumentasikan hasil pada repository.

---

## Checklist ringkas

* [ ] Memahami perbedaan InfoSec dan cybersecurity.
* [ ] Menjelaskan CIA triad dengan contoh.
* [ ] Mengategorikan kontrol: preventive, detective, corrective.
* [ ] Menilai risiko sederhana dan treatment.
* [ ] Menyusun kebijakan dasar yang jelas.
* [ ] Menjelaskan tahapan incident response.
* [ ] Memahami ATT&CK secara garis besar.
* [ ] Menentukan metrik KPI dan KRI awal.

---

## Glosarium mini

* Asset: sesuatu bernilai yang dilindungi.
* Threat: sesuatu yang berpotensi merusak.
* Vulnerability: kelemahan yang dapat dieksploitasi.
* Exploit: teknik pemicu kelemahan.
* Risk appetite: toleransi risiko organisasi.
* Control: mekanisme pengendalian risiko.
* Baseline: konfigurasi minimum yang disyaratkan.
* Playbook: panduan langkah operasional.
* EDR: endpoint detection and response.
* SIEM: security information and event management.

---

## Referensi lanjutan

**Kerangka dan standar**

* [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework)
* [ISO/IEC 27001 Overview](https://www.iso.org/isoiec-27001-information-security.html)
* [ISO/IEC 27002 Guide](https://www.iso.org/standard/75652.html)
* [CIS Controls v8](https://www.cisecurity.org/controls/v8)

**Manajemen risiko**

* [NIST SP 800-30](https://csrc.nist.gov/publications/detail/sp/800-30/rev-1/final)

**Incident response**

* [NIST SP 800-61r2](https://csrc.nist.gov/publications/detail/sp/800-61/rev-2/final)

**Threat intel**

* [MITRE ATT&CK](https://attack.mitre.org/)

**Aplikasi dan web**

* [OWASP Top 10](https://owasp.org/www-project-top-ten/)
* [OWASP SAMM](https://owaspsamm.org/)

**Panduan operasional**

* [SANS Reading Room](https://www.sans.org/white-papers/)
* [ENISA Publications](https://www.enisa.europa.eu/publications)

---

## Kontribusi

* Fork repository ini.
* Buat branch fitur terpisah.
* Gunakan commit message yang jelas.
* Ajukan pull request ringkas.

---

[⬆️ Kembali ke atas](#modul-04-pengenalan-security)
