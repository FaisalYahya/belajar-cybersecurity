# modul-03-linux-dasar

Pengantar Linux untuk pemula cybersecurity.  
Modul ini fokus praktik.  
Bahas konsep, perintah, dan kebiasaan kerja.

> [!TIP]
> Ketik perintah langsung di terminal.  
> Baca `man` sebelum googling.

## Daftar Isi
- [Tujuan belajar](#tujuan-belajar)
- [Prasyarat](#prasyarat)
- [Ekosistem Linux](#ekosistem-linux)
- [Navigasi shell](#navigasi-shell)
- [Man pages dan bantuan](#man-pages-dan-bantuan)
- [Filesystem dan FHS](#filesystem-dan-fhs)
- [Permission dan kepemilikan](#permission-dan-kepemilikan)
- [ACL dan atribut file](#acl-dan-atribut-file)
- [Proses dan layanan](#proses-dan-layanan)
- [Paket dan repositori](#paket-dan-repositori)
- [Jaringan di Linux](#jaringan-di-linux)
- [Teks tooling](#teks-tooling)
- [Shell scripting](#shell-scripting)
- [Penjadwalan tugas](#penjadwalan-tugas)
- [Penyimpanan dan mount](#penyimpanan-dan-mount)
- [Logging dan observabilitas](#logging-dan-observabilitas)
- [SSH dasar](#ssh-dasar)
- [Keamanan dasar](#keamanan-dasar)
- [Latihan cepat](#latihan-cepat)
- [Cheat sheet perintah](#cheat-sheet-perintah)
- [Checklist ringkas](#checklist-ringkas)
- [Glosarium mini](#glosarium-mini)
- [Referensi lanjutan](#referensi-lanjutan)
- [Kontribusi](#kontribusi)

---

## Tujuan belajar
- Memahami fondasi Linux untuk operasi dan keamanan.  
- Menguasai perintah inti terminal.  
- Menulis skrip shell sederhana.  
- Melakukan troubleshooting sistem dasar.

## Prasyarat
- Terbiasa dengan command line dasar.  
- VM Linux siap untuk latihan.  
- Koneksi internet untuk repositori.  
- Akses hak `sudo` di lab.

---

## Ekosistem Linux
- Kernel Linux adalah inti sistem.  
- *Distribution* mengemas kernel dan userspace.  
- Keluarga umum: Debian, RHEL, Arch, SUSE.  
- Rilis LTS cenderung stabil.  
- Rolling release lebih mutakhir, berisiko.

**Referensi cepat**
- [Arch Wiki](https://wiki.archlinux.org)  
- [Ubuntu Docs](https://help.ubuntu.com)  
- [Red Hat Docs](https://access.redhat.com/documentation/en-us/)  

---

## Navigasi shell
- Shell umum: bash, zsh, fish.  
- Direktori kerja saat ini: `pwd`.  
- Pindah direktori: `cd`.  
- Daftar file: `ls -la`.  
- Buat file kosong: `touch file.txt`.  
- Salin file: `cp a b`.  
- Pindah atau ganti nama: `mv a b`.  
- Hapus aman: `rm -i file`.

**Pipe dan redirection**
- Gabungkan perintah dengan `|`.  
- Tulis ke file dengan `>`.  
- Tambah ke file dengan `>>`.  
- Arahkan error dengan `2>`.

---

## Man pages dan bantuan
- Dokumentasi bawaan ada di `man`.  
- Contoh: `man ls`.  
- Opsi singkat: `command --help`.  
- Cari halaman `man -k keyword`.  
- Baca contoh `tldr` untuk ringkas.

**Referensi cepat**
- [man7.org](https://man7.org/linux/man-pages/)  
- [tldr pages](https://tldr.sh)  
- [Explainshell](https://explainshell.com)

---

## Filesystem dan FHS
- FHS mengatur struktur direktori standar.  
- `/` adalah akar filesystem.  
- `/bin` berisi perintah penting.  
- `/sbin` berisi perintah admin.  
- `/usr` berisi aplikasi dan library.  
- `/var` berisi data berubah.  
- `/etc` berisi konfigurasi sistem.  
- `/home` berisi data pengguna.  
- `/tmp` untuk file sementara.  
- `/proc` mengekspose informasi kernel.  
- `/dev` berisi device file.  
- `/sys` antarmuka kernel modern.

**Referensi cepat**
- [Filesystem Hierarchy Standard](https://refspecs.linuxfoundation.org/FHS_3.0/fhs-3.0.pdf)

---

## Permission dan kepemilikan
- Tiga subjek: user, group, others.  
- Tiga izin: read, write, execute.  
- Bentuk simbolik: `rwxr-x---`.  
- Bentuk oktal: `750`.  
- Ubah izin: `chmod 640 file`.  
- Ubah kepemilikan: `chown user:group file`.  
- Ubah grup: `chgrp group file`.  
- Atur `umask` untuk default izin.

**Bit khusus**
- SUID menjalankan dengan identitas pemilik.  
- SGID mewariskan grup direktori.  
- Sticky mencegah penghapusan oleh selain pemilik.  
- Contoh: `/tmp` memakai sticky bit.

**Referensi cepat**
- [GNU Coreutils chmod](https://www.gnu.org/software/coreutils/manual/html_node/chmod-invocation.html)

---

## ACL dan atribut file
- ACL memberi izin lebih granular.  
- Lihat ACL: `getfacl file`.  
- Atur ACL: `setfacl -m u:alice:r file`.  
- Atribut tambahan via `chattr`.  
- Lihat atribut: `lsattr`.

**Referensi cepat**
- [ACL on Linux](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/9/html/security_hardening/access-control-lists_acl)

---

## Proses dan layanan
- Daftar proses: `ps aux`.  
- Pantau proses: `top` atau `htop`.  
- Hentikan proses: `kill PID`.  
- *Niceness* mengatur prioritas CPU.  
- Layanan dikelola oleh `systemd`.  
- Kelola layanan: `systemctl status ssh`.  
- Mulai dan aktifkan: `systemctl enable --now ssh`.  
- Lihat log unit: `journalctl -u ssh`.

**Referensi cepat**
- [systemd manuals](https://www.freedesktop.org/software/systemd/man/)  
- [htop](https://htop.dev/)

---

## Paket dan repositori
- Debian/Ubuntu memakai `apt`.  
- RHEL/Fedora memakai `dnf`.  
- Arch memakai `pacman`.  
- SUSE memakai `zypper`.

**Contoh APT**
```bash
sudo apt update
sudo apt upgrade
sudo apt install htop
apt-cache policy htop

