# modul-05-web-security-dasar

Dasar keamanan web untuk pemula cybersecurity.  
Fokus pada serangan umum dan mitigasinya.  
Utamakan prinsip, bukan trik semata.

> [!TIP]
> Latih di lab aman seperti Web Security Academy.  
> Dokumentasikan temuan dan perbaikannya.

> [!WARNING]
> Uji hanya pada sistem berizin.  
> Hormati hukum dan privasi data.

## Daftar Isi
- [Tujuan belajar](#tujuan-belajar)
- [Prasyarat](#prasyarat)
- [Dasar HTTP dan web](#dasar-http-dan-web)
- [Sesi, cookie, dan state](#sesi-cookie-dan-state)
- [Authentication dan authorization](#authentication-dan-authorization)
- [Same-Origin Policy dan CORS](#same-origin-policy-dan-cors)
- [Security headers dan CSP](#security-headers-dan-csp)
- [OWASP Top 10 ringkas](#owasp-top-10-ringkas)
- [XSS](#xss)
- [Injection: SQL, NoSQL, OS](#injection-sql-nosql-os)
- [Path traversal dan file upload](#path-traversal-dan-file-upload)
- [Broken access control dan IDOR](#broken-access-control-dan-idor)
- [SSRF dan deserialisasi tidak aman](#ssrf-dan-deserialisasi-tidak-aman)
- [API security dasar](#api-security-dasar)
- [TLS, HTTPS, dan HSTS](#tls-https-dan-hsts)
- [Rate limiting dan anti brute-force](#rate-limiting-dan-anti-brute-force)
- [Dependency dan supply chain](#dependency-dan-supply-chain)
- [Logging, monitoring, dan audit](#logging-monitoring-dan-audit)
- [Threat modeling cepat](#threat-modeling-cepat)
- [Latihan cepat](#latihan-cepat)
- [Cheat sheet](#cheat-sheet)
- [Checklist ringkas](#checklist-ringkas)
- [Glosarium mini](#glosarium-mini)
- [Referensi lanjutan](#referensi-lanjutan)
- [Kontribusi](#kontribusi)

---

## Tujuan belajar
- Memahami cara kerja web secara aman.  
- Mengenali kerentanan web paling umum.  
- Menerapkan mitigasi yang praktis.  
- Menilai risiko pada aplikasi web.

## Prasyarat
- Dasar jaringan dan Linux sudah dikuasai.  
- Mengerti HTTP dasar dan HTML sederhana.  
- Siap belajar dengan alat testing.

---

## Dasar HTTP dan web
- HTTP adalah protokol tanpa state.  
- Resource diakses dengan method standar.  
- Contoh: GET, POST, PUT, DELETE, PATCH.  
- Status code membantu diagnosa masalah.  
- Header membawa metadata penting.

**Contoh `curl`**
```bash
curl -i https://example.com
curl -X POST -d 'a=1&b=2' https://example.com/form
````

---

## Sesi, cookie, dan state

* Server melacak sesi melalui cookie.
* Tandai cookie `Secure` dan `HttpOnly`.
* Gunakan `SameSite` untuk mencegah CSRF.
* Simpan session server-side bila memungkinkan.
* Hindari data sensitif di cookie.

**Contoh Set-Cookie**

```http
Set-Cookie: sid=...; Secure; HttpOnly; SameSite=Lax; Path=/; Max-Age=1800
```

---

## Authentication dan authorization

* AuthN memverifikasi identitas pengguna.
* AuthZ mengatur hak akses pengguna.
* Gunakan MFA untuk keamanan lebih kuat.
* Simpan hash password dengan KDF modern.
* Hindari roll-your-own auth.

**JWT praktik aman**

* Tanda tangani dengan algoritma kuat.
* Atur `exp` dan `aud` yang tepat.
* Rotasi kunci secara berkala.

---

## Same-Origin Policy dan CORS

* SOP membatasi interaksi antar origin.
* CORS membuka akses terkontrol lintas origin.
* Hindari `'*'` pada header sensitif.
* Validasi `Origin` pada sisi server.

**Header CORS contoh**

```http
Access-Control-Allow-Origin: https://app.example.com
Access-Control-Allow-Methods: GET, POST
Access-Control-Allow-Credentials: true
```

---

## Security headers dan CSP

* Tambahkan header keamanan standar.
* Gunakan CSP untuk menahan XSS.
* Aktifkan HSTS pada domain HTTPS.
* Set `X-Frame-Options` untuk anti clickjacking.

**Contoh CSP ketat**

```http
Content-Security-Policy: default-src 'self'; frame-ancestors 'none'; base-uri 'self'
```

**Node.js Helmet**

```js
import helmet from "helmet";
app.use(helmet());
```

---

## OWASP Top 10 ringkas

* Broken Access Control sering paling berbahaya.
* Cryptographic Failures menyebabkan kebocoran data.
* Injection menyerang query dan perintah.
* Insecure Design melemahkan arsitektur awal.
* Security Misconfiguration sangat umum ditemukan.
* Vulnerable Components membuka celah rantai pasok.
* Identification and Authentication Failures umum terjadi.
* Software and Data Integrity Failures berbahaya.
* Security Logging and Monitoring Failures memperparah insiden.
* SSRF menyalahgunakan kemampuan sisi server.

---

## XSS

* XSS menyuntikkan skrip ke halaman.
* Tipe utama: reflected, stored, DOM-based.
* Mitigasi dengan **output encoding** kontekstual.
* Gunakan CSP untuk lapisan tambahan.
* Validasi input membantu hygiene.

**Contoh encoding HTML**

```js
function escapeHTML(s){return s.replace(/[&<>"']/g, m=>({"&":"&amp;","<":"&lt;",">":"&gt;","\"":"&quot;","'":"&#39;"}[m]))}
```

---

## Injection: SQL, NoSQL, OS

* Injection terjadi saat input memodifikasi perintah.
* Gunakan **parameterized queries** selalu.
* Jangan konkatenasi input mentah.
* Sanitasi dan validasi tipe data.

**Parameterized SQL (Python)**

```python
cur.execute("SELECT * FROM users WHERE id = ?", (user_id,))
```

**Command execution aman**

```python
subprocess.run(["ls","-la"], check=True)
```

---

## Path traversal dan file upload

* Traversal mengakses file di luar direktori.
* Normalisasi path sebelum akses.
* Batasi direktori dengan chroot atau jail.
* Validasi dan scan file upload.
* Simpan upload di storage terisolasi.

---

## Broken access control dan IDOR

* IDOR mengekspos data melalui identifier.
* Jangan percaya ID dari klien.
* Enforce cek otorisasi pada setiap request.
* Gunakan policy server-side yang konsisten.

---

## SSRF dan deserialisasi tidak aman

* SSRF memaksa server memanggil endpoint internal.
* Gunakan allowlist host dan skema.
* Blok metadata IP dan loopback.
* Deserialisasi tidak aman memicu eksekusi kode.
* Gunakan format aman dan whitelisting tipe.

---

## API security dasar

* Treat API seperti aplikasi biasa.
* Gunakan auth yang kuat dan scoped.
* Validasi input pada setiap endpoint.
* Rate limiting untuk mencegah penyalahgunaan.
* Log detail cukup, tanpa data sensitif.

**API key dan secret**

* Simpan di secret manager.
* Jangan commit ke repository.

---

## TLS, HTTPS, dan HSTS

* Gunakan TLS modern dan kuat.
* Nonaktifkan protokol lemah dan cipher lawas.
* Aktifkan HSTS untuk domain utama.
* Terapkan redirect 301 ke HTTPS.

**Inspeksi cepat sertifikat**

```bash
openssl s_client -connect example.com:443 -servername example.com </dev/null
```

---

## Rate limiting dan anti brute-force

* Batasi percobaan login per IP dan akun.
* Tambah penundaan eksponensial saat gagal.
* Gunakan captcha jika diperlukan.
* Monitor pola anomali autentikasi.

**Express rate limit contoh**

```js
import rateLimit from "express-rate-limit";
app.use("/login", rateLimit({ windowMs: 15*60*1000, max: 20 }));
```

---

## Dependency dan supply chain

* Inventaris semua dependency.
* Pin versi dengan perhatian.
* Perbarui cepat saat ada CVE kritis.
* Verifikasi integritas paket bila mungkin.
* Hindari paket tidak tepercaya.

---

## Logging, monitoring, dan audit

* Log event auth, akses, dan perubahan konfigurasi.
* Hindari menyimpan password atau token.
* Kirim log ke SIEM terpusat.
* Buat alert untuk pola serangan umum.

---

## Threat modeling cepat

* Identifikasi aset, aktor, dan alur data.
* Gunakan STRIDE sebagai panduan sederhana.
* Catat asumsi dan kontrol mitigasi.
* Prioritaskan risiko dengan dampak terbesar.

---

## Latihan cepat

* Audit header keamanan pada situs pribadi.
* Tambahkan HSTS dan CSP yang aman.
* Perbaiki XSS pada form demo.
* Ubah query menjadi parameterized.
* Tambahkan rate limiting pada login.
* Simulasikan CSRF dan pasang token.
* Dokumentasikan sebelum dan sesudahnya.

---

## Cheat sheet

**curl**

```bash
curl -I https://example.com
curl -s -o /dev/null -w "%{http_code}\n" https://example.com
```

**Nmap TLS (lab berizin)**

```bash
nmap --script ssl-enum-ciphers -p 443 example.com
```

**ZAP / Burp**

* Rekam request dan analisis parameter.
* Uji input dan respon server.

**Security headers cepat**

```http
X-Content-Type-Options: nosniff
X-Frame-Options: DENY
Referrer-Policy: no-referrer
Permissions-Policy: geolocation=(), camera=()
```

---

## Checklist ringkas

* [ ] Semua endpoint memerlukan auth yang tepat.
* [ ] Validasi input dan lakukan output encoding.
* [ ] Query memakai parameterized queries.
* [ ] Header keamanan terpasang dan benar.
* [ ] TLS kuat dan HSTS aktif.
* [ ] CORS disetel minimal dan spesifik.
* [ ] Rate limiting di endpoint sensitif.
* [ ] Logging aman dan cukup untuk audit.
* [ ] Dependency dikelola dan dipantau CVE.
* [ ] Playbook respons web disiapkan.

---

## Glosarium mini

* XSS: injeksi skrip pada halaman web.
* CSRF: pemalsuan aksi lintas situs.
* IDOR: akses langsung objek tanpa cek otorisasi.
* CSP: kebijakan sumber konten halaman.
* HSTS: paksa akses HTTPS saja.
* SOP: kebijakan asal yang sama.
* JWT: token JSON bertanda tangan.
* CSRF Token: token anti aksi palsu.
* CVE: katalog kerentanan publik.
* CVSS: skor tingkat keparahan.

---

## Referensi lanjutan

**Belajar interaktif**

* [PortSwigger Web Security Academy](https://portswigger.net/web-security)
* [OWASP Juice Shop](https://owasp.org/www-project-juice-shop/)

**Standar dan panduan**

* [OWASP Top 10](https://owasp.org/www-project-top-ten/)
* [OWASP ASVS](https://owasp.org/www-project-application-security-verification-standard/)
* [OWASP Cheat Sheet Series](https://cheatsheetseries.owasp.org/)

**Dokumentasi teknis**

* [MDN Web Docs: HTTP](https://developer.mozilla.org/docs/Web/HTTP)
* [MDN: CORS](https://developer.mozilla.org/docs/Web/HTTP/CORS)
* [MDN: CSP](https://developer.mozilla.org/docs/Web/HTTP/CSP)

**Alat dan audit**

* [OWASP ZAP](https://www.zaproxy.org/)
* [Burp Suite Docs](https://portswigger.net/burp/documentation)
* [SSL Labs Test](https://www.ssllabs.com/ssltest/)
* [Mozilla Observatory](https://observatory.mozilla.org/)

---

## Kontribusi

* Fork repository ini.
* Buat branch fitur terpisah.
* Gunakan commit message yang jelas.
* Ajukan pull request ringkas.

---

[⬆️ Kembali ke atas](#modul-05-web-security-dasar)

