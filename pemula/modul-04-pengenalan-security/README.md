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

