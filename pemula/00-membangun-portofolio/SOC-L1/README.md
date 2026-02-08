# SOC Analyst (L1) Portfolio Guide

Panduan ini berisi langkah teknis mendetail untuk membangun Home Lab, mensimulasikan serangan siber nyata, dan—yang paling penting—cara mendokumentasikannya agar dilirik oleh recruiter.

---

## 🏗️ Bagian 1: Arsitektur & Persiapan

### 1.1 Topologi Lab
Kita akan membuat jaringan terisolasi (Safe Zone) di dalam laptop.
* **Attacker (Red Team):** Kali Linux.
* **Victim (Endpoint):** Windows 10.
* **Monitoring (Blue Team):** Splunk Enterprise (Log Collector & SIEM).

### 1.2 Persiapan Software
Download bahan-bahan berikut (Gratis/Trial):
1.  **Virtualisasi:** [VMware Workstation Player](https://www.vmware.com/products/workstation-player.html) atau VirtualBox.
2.  **Kali Linux:** [Installer Image (ISO)](https://www.kali.org/get-kali/).
3.  **Windows 10:** [Enterprise Evaluation (90 Days)](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-10-enterprise).
4.  **Splunk:** [Splunk Enterprise Free Trial](https://www.splunk.com/en_us/download/splunk-enterprise.html).
5.  **Sysmon:** [Sysinternals Suite](https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon).

---

## 🛠️ Bagian 2: Setup Langkah demi Langkah

### Langkah 1: Konfigurasi Jaringan Virtual (PENTING)
Agar aman dan antar-VM bisa saling ping:
* **Di VMware/VirtualBox:** Set Network Adapter kedua VM (Kali & Windows) ke mode **NAT Network** atau **Host-Only**.
* *Jangan* gunakan "Bridged" (agar serangan tidak bocor ke WiFi rumah).

### Langkah 2: Setup Korban (Windows 10)
1.  **Instalasi:** Install Windows 10 di VM.
2.  **Matikan Pertahanan:**
    * Buka *Windows Security* > *Virus & threat protection* > *Manage settings*.
    * **OFF**-kan "Real-time protection". (Supaya kita bisa menjalankan tool simulasi serangan tanpa diblokir).
3.  **Install Sysmon (Mata-mata Log):**
    * Download [Sysmon Config dari SwiftOnSecurity](https://github.com/SwiftOnSecurity/sysmon-config). Simpan sebagai `sysmonconfig.xml`.
    * Buka PowerShell (Run as Administrator).
    * Jalankan: `sysmon64.exe -i sysmonconfig.xml`
4.  **Cek IP:** Buka CMD, ketik `ipconfig`. Catat IP-nya (misal: `192.168.10.5`).

### Langkah 3: Setup Monitoring (Splunk)
1.  **Install:** Jalankan installer Splunk di dalam VM Windows (atau VM terpisah jika RAM >16GB).
2.  **Login:** Buka browser di `http://localhost:8000`.
3.  **Ingest Data (Memasukkan Log):**
    * Klik **Settings** > **Add Data**.
    * Pilih **Local Event Logs**.
    * Pilih log group: **Application**, **Security**, **System**.
    * *Penting:* Cari dan centang **Microsoft-Windows-Sysmon/Operational**.
    * Klik Next > Save.

### Langkah 4: Setup Penyerang (Kali Linux)
1.  **Instalasi:** Install Kali Linux di VM.
2.  **Cek Koneksi:** Buka terminal, ketik `ping [IP_WINDOWS]`. Jika reply, setup berhasil.

---

## ⚔️ Bagian 3: Simulasi Proyek (Hands-on)

Berikut adalah 3 proyek wajib untuk portofolio L1.

### Proyek A: Deteksi Serangan Brute Force (RDP)
**Skenario:** Penyerang mencoba menebak password Administrator secara paksa.

1.  **Serangan (Kali Linux):**
    Gunakan `Hydra` (tool penebak password).
    ```bash
    # Ganti 192.168.x.x dengan IP Windows
    hydra -l Administrator -P /usr/share/wordlists/rockyou.txt rdp://192.168.x.x
    ```
2.  **Deteksi (Splunk):**
    Cari Event ID **4625** (Logon Failure).
    ```splunk
    index=* EventCode=4625 
    | stats count by SourceNetworkAddress, TargetUserName 
    | where count > 10
    ```

### Proyek B: Deteksi Persistence (Backdoor User)
**Skenario:** Penyerang berhasil masuk dan membuat akun rahasia agar bisa kembali lagi nanti.

1.  **Serangan (Windows CMD):**
    Jalankan sebagai Administrator (seolah-olah attacker sudah masuk).
    ```cmd
    net user hacker Jahat123! /add
    net localgroup administrators hacker /add
    ```
2.  **Deteksi (Splunk):**
    Cari Event ID **4720** (User Created) dan **4732** (Member Added to Group).
    ```splunk
    index=* (EventCode=4720 OR EventCode=4732)
    | table _time, EventCode, TargetUserName, SubjectUserName
    ```

### Proyek C: Deteksi Teknik Obfuscation (Malware)
**Skenario:** Penyerang menyembunyikan perintah jahat menggunakan Base64 encoding.

1.  **Serangan (Windows PowerShell):**
    ```powershell
    powershell -e ZWNobyAiSGFja2VkIGJ5IEZhaXNhbCI=
    # (Ini adalah perintah "echo Hacked by Faisal" yang disandikan)
    ```
2.  **Deteksi (Splunk + Sysmon):**
    Log Windows biasa tidak melihat isi command line, tapi **Sysmon (Event ID 1)** bisa.
    ```splunk
    index=* source="*sysmon*" EventCode=1 Image="*powershell.exe*"
    | regex CommandLine=".*[A-Za-z0-9+/]{20,}=*"
    ```

---

## 📝 Bagian 4: Struktur Laporan Portofolio

Jangan hanya screenshot. Tulis laporan seperti seorang analis profesional. Buat repository di GitHub (misal: `My-SOC-Portfolio`) dan buat file Markdown untuk setiap proyek.

### Template Laporan (Copy-Paste ini ke GitHub Anda)

# Laporan Insiden: Percobaan Brute Force RDP

**Tanggal:** 8 Februari 2026
**Analyst:** Faisal Yahya
**Tools:** Splunk, Sysmon, Hydra

## 1. Executive Summary
Pada tanggal 8 Februari 2026, sistem monitoring mendeteksi lonjakan aktivitas autentikasi gagal pada endpoint `WIN-HR-01`. Investigasi lanjut mengonfirmasi adanya serangan Brute Force melalui protokol RDP yang berasal dari IP internal `192.168.10.100`. Serangan berhasil dihentikan, namun penyerang sempat mencoba membuat user backdoor.

## 2. Metodologi Serangan (The Attack)
Penyerang menggunakan tool **Hydra** untuk melakukan dictionary attack.
* **Target:** Administrator
* **Protokol:** RDP (Port 3389)
* **Bukti:**
    [Screenshot Terminal Kali Linux saat Hydra berjalan]

## 3. Analisis & Deteksi (The Defense)
Analisis dilakukan menggunakan Splunk dengan query berikut untuk mendeteksi Event ID 4625 (Logon Failure).

**Query SPL:**
`index=main EventCode=4625 | stats count by SourceNetworkAddress`

**Hasil Temuan:**
* Ditemukan 450 percobaan login gagal dalam kurun waktu 2 menit.
* IP Sumber: 192.168.10.100
* Target User: Administrator
* [Screenshot Dashboard Splunk memperlihatkan grafik lonjakan]

Selain itu, ditemukan indikator persistensi (Event ID 4720) dimana user `hacker` dibuat tepat setelah login berhasil.

## 4. Remediasi & Rekomendasi
1.  **Isolasi:** Endpoint diputuskan dari jaringan.
2.  **Pembersihan:** User `hacker` dihapus.
3.  **Hardening:**
    * Mengubah port default RDP.
    * Menerapkan kebijakan *Account Lockout* (kunci akun setelah 5x gagal).
    * Mewajibkan VPN untuk akses RDP.

---

## ✅ Checklist Akhir
1.  [ ] Lab sudah berjalan (Kali & Windows saling ping).
2.  [ ] Log Sysmon masuk ke Splunk.
3.  [ ] Minimal 3 skenario serangan dijalankan & dideteksi.
4.  [ ] Laporan di-upload ke GitHub/Medium/LinkedIn.
5.  [ ] Link portofolio dicantumkan di CV (di bawah nama/kontak).

