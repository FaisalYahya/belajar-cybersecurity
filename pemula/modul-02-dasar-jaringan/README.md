# modul-02-dasar-jaringan

Dasar jaringan untuk jalur cybersecurity.  
Modul ini melanjutkan modul dasar IT.  
Fokus pada konsep yang sering diuji.

> [!TIP]
> Visualkan paket data saat belajar.  
> Gunakan lab untuk eksperimen aman.

## Daftar Isi
- [Tujuan belajar](#tujuan-belajar)
- [Prasyarat](#prasyarat)
- [Peta konsep jaringan](#peta-konsep-jaringan)
- [Model OSI dan TCP/IP](#model-osi-dan-tcpip)
- [Perangkat jaringan](#perangkat-jaringan)
- [Media dan topologi](#media-dan-topologi)
- [IP dan subnetting](#ip-dan-subnetting)
- [ARP dan NDP](#arp-dan-ndp)
- [Port dan protokol](#port-dan-protokol)
- [DNS](#dns)
- [DHCP](#dhcp)
- [Switching dan VLAN](#switching-dan-vlan)
- [Routing dan NAT](#routing-dan-nat)
- [Wireless](#wireless)
- [Keamanan jaringan](#keamanan-jaringan)
- [Monitoring dan troubleshooting](#monitoring-dan-troubleshooting)
- [Kinerja dan QoS](#kinerja-dan-qos)
- [Latihan dan portofolio](#latihan-dan-portofolio)
- [Latihan cepat](#latihan-cepat)
- [Cheat sheet perintah](#cheat-sheet-perintah)
- [Checklist ringkas](#checklist-ringkas)
- [Glosarium mini](#glosarium-mini)
- [Referensi lanjutan](#referensi-lanjutan)
- [Kontribusi](#kontribusi)

---

## Tujuan belajar
- Memahami model jaringan dan alur data.  
- Menguasai subnetting dan pengalamatan IP.  
- Mengerti switching, routing, dan VLAN.  
- Mengenali protokol penting dan port umum.  
- Mempraktikkan troubleshooting yang sistematis.

## Prasyarat
- Menguasai materi modul dasar IT.  
- Terbiasa memakai command line dasar.  
- Memiliki lab virtual sederhana.

---

## Peta konsep jaringan
- Jaringan menghubungkan host untuk bertukar data.  
- Data berjalan melalui layer berurutan.  
- Setiap layer punya fungsi dan antarmuka.  
- Kontrol akses dan keamanan diterapkan berlapis.

---

## Model OSI dan TCP/IP
- OSI punya tujuh layer utama.  
- TCP/IP memakai empat atau lima layer.  
- Pahami enkapsulasi dan dekap data.  
- Kenali PDU: bit, frame, packet, segment.  
- MTU memengaruhi fragmentasi paket.  
- Perhatikan TTL, MSS, dan jendela TCP.

---

## Perangkat jaringan
- Hub membanjiri semua port.  
- Switch belajar MAC dan mem-forward cerdas.  
- Router mengarahkan paket antar jaringan.  
- Firewall memfilter trafik berdasarkan aturan.  
- IDS/IPS memonitor dan mencegah serangan.  
- Load balancer membagi beban layanan.  
- Proxy menyisipkan lapisan kontrol aplikasi.

---

## Media dan topologi
- Kabel tembaga untuk jarak pendek.  
- Fiber untuk jarak jauh dan bandwidth tinggi.  
- Nirkabel memakai spektrum 2.4, 5, dan 6 GHz.  
- Konektor umum: RJ45, SFP, LC.  
- Kategori kabel: Cat5e, Cat6, Cat6A.  
- Topologi umum: star, mesh, bus, ring.

---

## IP dan subnetting
- IPv4 menggunakan 32 bit alamat.  
- Notasi umum: alamat dan mask atau CIDR.  
- Alamat privat: 10/8, 172.16/12, 192.168/16.  
- Default gateway menghubungkan keluar subnet.  
- Broadcast mengirim ke semua host subnet.  
- Subnetting membagi jaringan jadi segmen logis.  
- IPv6 memakai 128 bit alamat.  
- Notasi heksadesimal dipisah tanda titik dua.  
- Link-local memakai prefix fe80::.  
- SLAAC dan DHCPv6 mengonfigurasi alamat otomatis.

**Contoh hitung subnet**
```text
Jaringan: 192.168.10.0/24
/26 memberi 4 subnet, 62 host per subnet.
Rentang: 192.168.10.0/26, .64/26, .128/26, .192/26
````

---

## ARP dan NDP

* ARP memetakan IP ke alamat MAC.
* Cache ARP menyimpan hasil sementara.
* Poisoning ARP memungkinkan serangan MITM.
* IPv6 memakai NDP untuk tetangga.
* NDP memakai ICMPv6 untuk resolusi alamat.

---

## Port dan protokol

* Port mengidentifikasi layanan pada host.
* TCP andal, berorientasi koneksi.
* UDP ringan, tanpa koneksi.
* ICMP untuk pesan kontrol jaringan.
* Handshake TCP: SYN, SYN-ACK, ACK.
* Port penting: 22, 53, 80, 123, 443.
* Layanan umum: SSH, DNS, HTTP, NTP, HTTPS.
* Email: SMTP, IMAP, POP3.
* Administrasi: RDP, WinRM, SNMP.
* File: SMB, NFS, SFTP, FTPS.

---

## DNS

* DNS menerjemahkan nama menjadi alamat.
* Tipe record: A, AAAA, CNAME, MX, TXT, SRV, NS.
* Resolver rekursif melakukan pencarian bertahap.
* Server otoritatif menyimpan zona resmi.
* TTL mengendalikan waktu cache.
* DNSSEC menandatangani record dengan kripto.
* DoT dan DoH mengenkripsi kueri.

**Perintah DNS umum**

```bash
dig +short A example.com
dig +short AAAA example.com
dig +trace example.com
nslookup -type=txt example.com
```

---

## DHCP

* DHCP memberikan alamat dan konfigurasi otomatis.
* Proses DORA: Discover, Offer, Request, Acknowledge.
* Opsi penting: gateway, DNS, domain, waktu.
* Risiko: rogue DHCP dan poisoning.

---

## Switching dan VLAN

* Switch mempelajari MAC pada setiap port.
* Tabel MAC menentukan forwarding.
* Broadcast domain dibatasi oleh VLAN.
* VLAN memisahkan trafik secara logis.
* 802.1Q menandai frame bertag VLAN.
* Port access untuk endpoint tunggal.
* Port trunk membawa beberapa VLAN.
* STP mencegah loop pada layer dua.
* LACP menggabungkan beberapa link.

**Contoh konfigurasi VLAN (konsep)**

```text
VLAN 10: Users
VLAN 20: Servers
Port 1-10: access VLAN 10
Port 11-12: trunk VLAN 10,20
```

---

## Routing dan NAT

* Routing memindahkan paket antar jaringan.
* Route default menangani tujuan tidak dikenal.
* Routing statis dikelola manual.
* Routing dinamis memakai protokol khusus.
* Contoh protokol: OSPF, BGP, RIP.
* NAT menerjemahkan alamat privat ke publik.
* PAT memetakan banyak host ke satu alamat.
* VRF memisahkan tabel routing logis.

**Contoh traceroute**

```bash
traceroute 1.1.1.1
# Windows:
tracert 1.1.1.1
```

---

## Wireless

* 802.11 mendefinisikan jaringan nirkabel.
* SSID mengidentifikasi jaringan nirkabel.
* BSSID merepresentasikan alamat MAC AP.
* WPA2 sudah umum, WPA3 lebih aman.
* 802.1X mendukung otentikasi enterprise.
* Kanal tumpang tindih meningkatkan interferensi.
* Pilih kanal sesuai regulasi lokal.

---

## Keamanan jaringan

* Segmentation mengurangi dampak kompromi.
* ACL mengizinkan atau menolak trafik.
* Firewall menerapkan kebijakan berlapis.
* IDS/IPS mendeteksi dan menghentikan serangan.
* WAF melindungi aplikasi web.
* NAC membatasi akses perangkat tidak tepercaya.
* Ancaman umum: MITM, spoofing, poisoning, scanning.
* Nonaktifkan layanan yang tidak diperlukan.
* Terapkan patch secara berkala.

---

## Monitoring dan troubleshooting

* Observabilitas penting untuk keandalan.
* Gunakan ICMP untuk uji reachability.
* Traceroute memetakan jalur hop.
* NetFlow atau IPFIX mengukur pola trafik.
* SNMP memantau perangkat dan interface.
* Mirror port untuk analisis paket.
* Wireshark memeriksa paket secara detail.
* tcpdump menangkap paket dari terminal.
* Terapkan pendekatan per layer saat diagnosa.

**Contoh filter Wireshark**

```text
tcp.flags.syn==1 && tcp.flags.ack==0
dns && ip.addr==192.168.1.10
tls.handshake
```

**Contoh tcpdump**

```bash
sudo tcpdump -i eth0 -n "tcp port 443"
sudo tcpdump -i wlan0 -vvv icmp
```

---

## Kinerja dan QoS

* Latensi adalah waktu tempuh paket.
* Jitter adalah variasi latensi.
* Packet loss menurunkan kualitas layanan.
* Throughput berbeda dengan goodput.
* Bufferbloat menyebabkan latensi tinggi.
* QoS menandai dan memprioritaskan trafik.
* DSCP mengkodekan kelas layanan.
* Shaping mengatur laju keluar.
* Policing membatasi trafik berlebih.

---

## Latihan dan portofolio

* Buat topologi kecil di virtualisasi.
* Dokumentasikan desain dan alasan teknis.
* Catat hasil troubleshooting dan pembelajaran.
* Tulis ringkasan untuk portofolio publik.

---

## Latihan cepat

* Hitung subnet untuk jaringan rumahan.
* Buat dua VLAN dan uji isolasi.
* Lakukan traceroute ke beberapa tujuan.
* Tangkap handshake TCP dengan tcpdump.
* Analisis query DNS dengan Wireshark.
* Uji DoH memakai curl dan filter.
* Simulasikan NAT pada router virtual.

---

## Cheat sheet perintah

**Linux**

```bash
ip a
ip r
ip neigh
ss -tulpen
arp -n
dig +short example.com
mtr -rw 1.1.1.1
curl -I https://example.com
sudo tcpdump -i any -n port 53
```

**Windows**

```powershell
ipconfig /all
Get-NetIPConfiguration
Test-NetConnection google.com -Port 443
tracert 1.1.1.1
arp -a
netstat -ano
Resolve-DnsName example.com
```

---

## Checklist ringkas

* [ ] Memahami OSI dan TCP/IP.
* [ ] Menghitung subnet dengan percaya diri.
* [ ] Mengonfigurasi VLAN dan trunk sederhana.
* [ ] Menjelaskan routing statis dan dinamis.
* [ ] Memahami NAT dan PAT.
* [ ] Menggunakan dig, tcpdump, dan Wireshark.
* [ ] Mendiagnosa masalah memakai pendekatan layer.

---

## Glosarium mini

* Host: perangkat jaringan yang menjalankan layanan.
* Segment: unit data pada layer transport.
* Packet: unit data pada layer jaringan.
* Frame: unit data pada layer data link.
* MTU: ukuran maksimum payload frame.
* TTL: batas lompatan paket jaringan.
* NAT: penerjemahan alamat jaringan.
* VLAN: segmentasi logis pada layer dua.
* SSID: nama jaringan nirkabel.
* DSCP: penanda kelas layanan.

---

## Referensi lanjutan

**Konsep dasar dan visualisasi**

* [Practical Networking](https://www.practicalnetworking.net/)
* [Cloudflare Learning Center](https://www.cloudflare.com/learning/)
* [Cisco DevNet Networking Basics](https://developer.cisco.com/learning/networking/)

**Protokol dan standar**

* [IETF RFC 791 – IPv4](https://www.rfc-editor.org/rfc/rfc791)
* [IETF RFC 8200 – IPv6](https://www.rfc-editor.org/rfc/rfc8200)
* [IEEE 802.1Q VLAN](https://standards.ieee.org/standard/802_1Q-2022.html)

**DNS dan HTTP**

* [DNS 101 by NS1](https://ns1.com/what-is-dns)
* [MDN: HTTP Overview](https://developer.mozilla.org/docs/Web/HTTP/Overview)

**Troubleshooting dan capture**

* [Wireshark User Guide](https://www.wireshark.org/docs/wsug_html/)
* [tcpdump man page](https://www.tcpdump.org/manpages/tcpdump.1.html)
* [MTR documentation](https://github.com/traviscross/mtr)

---

## Kontribusi

* Fork repository ini.
* Buat branch fitur terpisah.
* Gunakan commit message yang jelas.
* Ajukan pull request ringkas.

---

[⬆️ Kembali ke atas](#modul-02-dasar-jaringan)

```
```
