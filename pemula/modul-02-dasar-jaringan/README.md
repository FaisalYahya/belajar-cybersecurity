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

