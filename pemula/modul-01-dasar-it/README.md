# modul-01-dasar-it

Dasar IT untuk jalur cybersecurity.
Gunakan modul ini sebagai peta belajar awal.
Fokus pada konsep inti sebelum alat canggih.

> [!TIP]
> Belajar perlahan atau sedikit2, tapi konsisten.
> Latih konsep di lab pribadi Anda.

## Daftar Isi

* [Tujuan belajar](#tujuan-belajar)
* [Prasyarat](#prasyarat)
* [Peta jalur karier](#peta-jalur-karier)
* [Konsep inti IT](#konsep-inti-it)
* [Jaringan komputer](#jaringan-komputer)
* [Sistem operasi](#sistem-operasi)
* [Baris perintah](#baris-perintah)
* [Pemrograman dasar](#pemrograman-dasar)
* [Web fundamentals](#web-fundamentals)
* [Dasar keamanan](#dasar-keamanan)
* [Kriptografi](#kriptografi)
* [Identitas dan akses](#identitas-dan-akses)
* [Keamanan jaringan](#keamanan-jaringan)
* [Cloud dan container](#cloud-dan-container)
* [Alat penting](#alat-penting)
* [Lingkungan lab](#lingkungan-lab)
* [Etika dan legal](#etika-dan-legal)
* [Latihan dan portofolio](#latihan-dan-portofolio)
* [Latihan cepat](#latihan-cepat)
* [Checklist ringkas](#checklist-ringkas)
* [Glosarium mini](#glosarium-mini)
* [Referensi lanjutan](#referensi-lanjutan)
* [Kontribusi](#kontribusi)

---

## Tujuan belajar

* Memahami fondasi IT untuk keamanan siber.
* Menyiapkan lingkungan lab yang aman.
* Mengetahui jalur peran keamanan.
* Menentukan rencana belajar realistis.

## Prasyarat

* Rasa ingin tahu tinggi.
* Akses komputer pribadi.
* Koneksi internet stabil.
* Waktu belajar konsisten setiap minggu.

## Peta jalur karier

* Blue Team: monitoring, incident response, hardening.
* Red Team: penetration testing, adversary emulation.
* Purple Team: kolaborasi serangan dan pertahanan.
* GRC: governance, risk, compliance, kebijakan, audit.
* SecOps: operasi keamanan harian.
* AppSec: keamanan aplikasi dan proses SDLC.
* Cloud Security: fokus cloud dan container.
* Identity Security: IAM, PAM, SSO, federation.

---

## Konsep inti IT

**Model mental penting**

* CIA triad: confidentiality, integrity, availability.
* Prinsip least privilege dan separation of duties.
* Defense in depth untuk kontrol berlapis.
* Threat modeling sejak awal desain.
* Zero Trust sebagai sikap desain.
* Risiko diukur, bukan sekadar ditakuti.

**Arsitektur komputer**

* Pahami CPU, memori, penyimpanan, dan I/O.
* Kenali proses, thread, dan context switching.
* Pelajari file system dan permission dasar.
* Monitoring memakai metrik dan log.

---

## Jaringan komputer

* Kuasai konsep OSI dan TCP/IP.
* IP addressing, subnetting, dan routing dasar.
* Bedakan TCP, UDP, dan ICMP.
* Nama domain, DNS, dan resolusi.
* HTTP, HTTPS, TLS, dan certificate pinning.
* Gunakan Wireshark untuk analisis paket awal.

**Perintah jaringan penting**

```bash
ip a
ip route
ss -tulpen
dig +short example.com
ping -c 4 1.1.1.1
curl -I https://example.com
```

---

## Sistem operasi

**Linux**

* Pahami distro umum: Ubuntu, Debian, Fedora, Kali.
* Konsep user, group, permission, dan sudo.
* Service, systemd, dan journald.
* Networking melalui ip, ss, dan nftables.

**Windows**

* Pahami registry, services, dan Event Viewer.
* Kenali Active Directory konsep dasar.
* Gunakan PowerShell untuk administrasi.

---

## Baris perintah

* Command line adalah alat wajib.
* Pelajari bash dasar dan scripting sederhana.
* Kenali PowerShell cmdlet dan pipeline.
* Gunakan package manager untuk efisiensi.

**Contoh Linux**

```bash
whoami
uname -a
id
ls -la
pwd
df -h
free -m
```

**Contoh PowerShell**

```powershell
Get-Process
Get-Service
Get-EventLog -LogName System -Newest 5
Test-NetConnection github.com -Port 443
```

---

## Pemrograman dasar

* Fokus pada Python untuk otomasi.
* Pelajari konsep variabel, tipe, fungsi, modul.
* Kenali struktur data penting.
* Gunakan virtual environment saat proyek.

**Contoh Python**

```python
import requests
r = requests.get("https://httpbin.org/status/200")
print(r.status_code)
```

---

## Web fundamentals

* Pahami cara web bekerja end-to-end.
* HTTP methods, status codes, dan headers.
* HTML, CSS, dan JavaScript dasar.
* Framework umum dan arsitektur REST.

---

## Dasar keamanan

* Ancaman umum: phishing, malware, ransomware, insider threat.
* Kerangka kerja: NIST CSF, ISO 27001.
* Kontrol: patching, hardening, backup, monitoring.
* Logging dan alerting yang dapat ditindaklanjuti.
* Incident response lifecycle yang ringkas.
* Gunakan playbook sederhana terlebih dulu.

---

## Kriptografi

* Symmetric vs asymmetric encryption.
* Kunci, nonce, IV, dan salt.
* Hashing untuk integritas, bukan kerahasiaan.
* TLS handshakes dan certificate chain.
* PKI dan konsep trust.
* Jangan bikin algoritma sendiri.

---

## Identitas dan akses

* Authentication, authorization, dan accounting (AAA).
* MFA sebagai standar minimal.
* OAuth 2.0 dan OIDC untuk web.
* Least privilege dan role based access control.
* Pahami session dan token management.

---

## Keamanan jaringan

* Segmentation dan microsegmentation.
* Firewall konsep stateful dan stateless.
* IDS/IPS dasar utilisasi.
* VPN dan secure remote access.
* Hardening router, switch, dan server.

---

## Cloud dan container

* Kenali AWS, Azure, dan GCP layanan dasar.
* Shared Responsibility Model sangat penting.
* Storage, network, compute, dan IAM di cloud.
* Container, images, registry, dan orchestration.
* Gunakan IaC seperti Terraform dengan hati-hati.
* Scanning container dan dependency.

---

## Alat penting

* Nmap untuk discovery dan enumeration.
* Wireshark untuk traffic capture.
* Burp Suite untuk web testing.
* Metasploit untuk lab eksploitasi.
* Sysinternals untuk Windows troubleshooting.
* osquery untuk visibilitas.
* YARA untuk signature hunting.
* Sigma dan KQL untuk deteksi.

**Contoh Nmap**

```bash
nmap -Pn -sV --top-ports 100 <target>
```

---

## Lingkungan lab

* Gunakan virtualisasi seperti VirtualBox atau VMware.
* Pisahkan jaringan lab dari jaringan utama.
* Gunakan NAT atau host-only untuk aman.
* Snapshot sebelum eksperimen berisiko.
* Pertimbangkan WSL atau Docker untuk cepat.
* Pakai image legal, bukan bajakan.

---

## Etika dan legal

* Hanya uji sistem yang Anda miliki.
* Dapatkan izin tertulis sebelum pengujian.
* Hormati privasi dan data sensitif.
* Ikuti hukum setempat dan kebijakan perusahaan.

> [!WARNING]
> Konten untuk edukasi.
> Tanggung jawab penggunaan ada pada Anda.

---

## Latihan dan portofolio

* Ikuti CTF pemula untuk belajar taktik.
* Bangun lab write-up di repository Anda.
* Buat catatan, bukan sekadar bookmark.
* Dokumentasikan proses dan hasil belajar.
* Kontribusi kecil ke proyek open-source.

---

## Latihan cepat

* Jalankan ping ke domain pilihan.
* Lacak traceroute ke layanan publik.
* Scan lokal dengan nmap terbatas.
* Tulis skrip Python sederhana.

---

## Checklist ringkas

* [ ] Memahami CIA triad dan dasar risiko.
* [ ] Menguasai command line dasar.
* [ ] Mengerti jaringan dan DNS dasar.
* [ ] Menyiapkan lab virtual aman.
* [ ] Menulis skrip Python sederhana.
* [ ] Membaca log dan membuat alert sederhana.
* [ ] Mengetahui etika dan batas hukum.

---

## Glosarium mini

* Asset: sesuatu bernilai yang dilindungi.
* Vulnerability: kelemahan yang dapat dieksploitasi.
* Threat: sesuatu yang berpotensi menimbulkan kerugian.
* Exploit: teknik untuk memanfaatkan vulnerability.
* Risk: kemungkinan kerugian dikalikan dampak.
* Control: mekanisme untuk mengurangi risiko.
* Attack surface: seluruh titik interaksi sistem.
* Hardening: penguatan konfigurasi dan layanan.

---

## Referensi lanjutan

**Dasar jaringan dan sistem**

* [Practical Networking](https://www.practicalnetworking.net/)
* [Linux Journey](https://linuxjourney.com/)
* [Red Hat: Linux Getting Started](https://www.redhat.com/en/resources/linux-getting-started)

**Keamanan umum**

* [OWASP Top 10](https://owasp.org/www-project-top-ten/)
* [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework)
* [CIS Controls v8](https://www.cisecurity.org/controls/v8)
* [MITRE ATT&CK](https://attack.mitre.org/)
* [Malware Traffic Analysis](https://www.malware-traffic-analysis.net/)

**Kriptografi**

* [Crypto 101](https://crypto101.io/)
* [Cloudflare: What is SSL/TLS](https://www.cloudflare.com/learning/ssl/what-is-ssl/)

**Cloud**

* [AWS Well-Architected](https://aws.amazon.com/architecture/well-architected/)
* [Azure Security Docs](https://learn.microsoft.com/azure/security/)
* [Google Cloud Security](https://cloud.google.com/security)

**Alat**

* [Nmap Book](https://nmap.org/book/)
* [Wireshark User Guide](https://www.wireshark.org/docs/)
* [Burp Suite Documentation](https://portswigger.net/burp/documentation)
* [Sysinternals Suite](https://learn.microsoft.com/sysinternals/)
* [osquery Documentation](https://osquery.io/)

**Latihan**

* [PortSwigger Web Security Academy](https://portswigger.net/web-security)
* [TryHackMe](https://tryhackme.com/)
* [Hack The Box Academy](https://academy.hackthebox.com/)
* [OverTheWire Wargames](https://overthewire.org/wargames/)
* [picoCTF](https://picoctf.org/)

---

## Kontribusi

* Fork repository ini.
* Buat branch fitur terpisah.
* Gunakan commit message yang jelas.
* Ajukan pull request ringkas.

---

[⬆️ Kembali ke atas](#modul-01-dasar-it)
