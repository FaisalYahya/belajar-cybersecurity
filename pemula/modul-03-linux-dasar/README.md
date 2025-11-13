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
````

**Contoh DNF**

```bash
sudo dnf check-update
sudo dnf upgrade --refresh
sudo dnf install htop
```

**Contoh Pacman**

```bash
sudo pacman -Syu
sudo pacman -S htop
```

**Referensi cepat**

* [APT Guide](https://wiki.debian.org/Apt)
* [DNF Manual](https://dnf.readthedocs.io)
* [Pacman](https://wiki.archlinux.org/title/Pacman)

---

## Jaringan di Linux

* Alamat dan link: `ip a`, `ip link`.
* Routing: `ip route`.
* Tabel ARP: `ip neigh`.
* Port terbuka: `ss -tulpen`.
* Uji koneksi: `ping` dan `traceroute`.
* DNS query: `dig` atau `resolvectl`.
* NetworkManager: `nmcli` untuk konfigurasi.

**Referensi cepat**

* [iproute2](https://wiki.linuxfoundation.org/networking/iproute2)
* [NetworkManager nmcli](https://developer.gnome.org/NetworkManager/stable/nmcli.html)
* [Wireshark Docs](https://www.wireshark.org/docs/)

---

## Teks tooling

* Lihat isi: `cat`, `less`.
* Filter baris: `grep -i`.
* Potong kolom: `cut -d`.
* Ubah teks: `sed` untuk substitusi.
* Olah kolom: `awk` untuk laporan.
* Urutkan: `sort`.
* Hapus duplikasi: `uniq -c`.
* Gabungkan pipeline dengan bijak.

**Referensi cepat**

* [GNU grep](https://www.gnu.org/software/grep/manual/)
* [GNU sed](https://www.gnu.org/software/sed/manual/)
* [GNU awk](https://www.gnu.org/software/gawk/manual/)

---

## Shell scripting

* Awali skrip dengan shebang.
* Contoh: `#!/usr/bin/env bash`.
* Gunakan `set -euo pipefail` dengan hati-hati.
* Pahami quoting dan ekspansi.
* Variabel lingkungan memengaruhi perilaku.
* Periksa keluar dengan `$?`.
* Tulis fungsi kecil dan teruji.
* Validasi dengan ShellCheck.

**Contoh skrip**

```bash
#!/usr/bin/env bash
set -euo pipefail
host=${1:-"example.com"}
if ping -c 1 "$host" >/dev/null 2>&1; then
  echo "Host reachable"
else
  echo "Host unreachable"
fi
```

**Referensi cepat**

* [Bash Reference Manual](https://www.gnu.org/software/bash/manual/)
* [Bash Hackers Wiki](http://wiki.bash-hackers.org/)
* [ShellCheck](https://www.shellcheck.net)

---

## Penjadwalan tugas

* Cron menjalankan tugas terjadwal.
* Edit jadwal: `crontab -e`.
* Format lima kolom waktu.
* Systemd timers alternatif modern.

**Contoh cron**

```cron
# Backup tiap jam
0 * * * * /usr/local/bin/backup.sh
```

**Referensi cepat**

* [crontab.guru](https://crontab.guru/)
* [systemd timers](https://www.freedesktop.org/software/systemd/man/systemd.timer.html)

---

## Penyimpanan dan mount

* Lihat disk: `lsblk`.
* Cek filesystem: `df -h`.
* Cek penggunaan: `du -sh *`.
* Mount sementara: `sudo mount`.
* Atur permanen di `/etc/fstab`.
* Swap meningkatkan elastisitas memori.
* LVM memudahkan manajemen volume.

**Contoh fstab**

```fstab
UUID=XXXX /data ext4 defaults,noatime 0 2
```

**Referensi cepat**

* [Ubuntu Server Guide: Storage](https://ubuntu.com/server/docs)
* [LVM Admin Guide](https://wiki.archlinux.org/title/LVM)

---

## Logging dan observabilitas

* Kernel ring: `dmesg`.
* Journal `systemd`: `journalctl`.
* Filter prioritas: `journalctl -p err`.
* Log unit: `journalctl -u ssh`.
* Rotasi log via `logrotate`.

**Referensi cepat**

* [journalctl manpage](https://www.freedesktop.org/software/systemd/man/journalctl.html)
* [logrotate](https://github.com/logrotate/logrotate)

---

## SSH dasar

* Buat kunci: `ssh-keygen -t ed25519`.
* Salin kunci: `ssh-copy-id user@host`.
* Nonaktifkan password login bila siap.
* Gunakan `~/.ssh/config` untuk kenyamanan.
* Transfer file via `scp` atau `rsync`.

**Contoh config**

```sshconfig
Host myserver
  HostName 203.0.113.10
  User alice
  IdentityFile ~/.ssh/id_ed25519
```

**Referensi cepat**

* [OpenSSH manual](https://man.openbsd.org/ssh)

---

## Keamanan dasar

* Gunakan `sudo`, bukan `root` langsung.
* Edit sudoers dengan `visudo`.
* Firewall sederhana dengan `ufw`.
* Atau pakai `nftables` untuk fleksibilitas.
* SELinux atau AppArmor menambah kontrol.
* Update rutin untuk patch keamanan.

**Contoh UFW**

```bash
sudo ufw default deny incoming
sudo ufw allow OpenSSH
sudo ufw enable
sudo ufw status
```

**Referensi cepat**

* [UFW](https://help.ubuntu.com/community/UFW)
* [nftables Wiki](https://wiki.nftables.org)
* [SELinux Project](https://selinuxproject.org/page/Main_Page)
* [AppArmor](https://wiki.ubuntu.com/AppArmor)

---

## Latihan cepat

* Jelajahi FHS dengan `tree / -L 1`.
* Buat user baru dan grup.
* Atur izin direktori proyek.
* Tulis skrip backup folder `~/docs`.
* Pasang `htop` dan analisis proses.
* Buka port SSH saja di `ufw`.
* Tangkap paket DNS dengan `tcpdump`.
* Otomatiskan update mingguan dengan cron.

---

## Cheat sheet perintah

```bash
# Navigasi
pwd; cd /etc; ls -la
# File
touch a; echo hi > a; cp a b; mv b c; rm -i c
# Pencarian
find /var/log -type f -name "*.log"
grep -Rin "error" /var/log
# Pemrosesan teks
cat file | sed 's/foo/bar/g' | awk '{print $1}' | sort | uniq -c
# Proses
ps aux | head
top
kill -9 <PID>
# Jaringan
ip a; ip r; ss -tulpen
ping -c 4 1.1.1.1
dig +short example.com
# Systemd
systemctl status ssh
journalctl -u ssh --since "today"
# Disk
lsblk; df -h; du -sh *
```

---

## Checklist ringkas

* [ ] Memahami FHS dan navigasi shell.
* [ ] Mengelola permission dan ACL dasar.
* [ ] Mengelola layanan dengan systemd.
* [ ] Memakai paket manager dengan aman.
* [ ] Melakukan tugas jaringan dasar.
* [ ] Menulis skrip bash sederhana.
* [ ] Menjadwalkan cron dengan benar.
* [ ] Mengelola mount dan `fstab`.
* [ ] Membaca log dengan `journalctl`.
* [ ] Mengamankan akses SSH dasar.

---

## Glosarium mini

* Shell: antarmuka perintah teks.
* Daemon: layanan berjalan di latar.
* Unit: objek layanan pada systemd.
* UID/GID: identitas user dan grup.
* Inode: metadata objek filesystem.
* Shebang: baris interpreter skrip.
* Exit code: status hasil perintah.
* ACL: izin tambahan per pengguna.
* Journal: sistem log `systemd`.
* Repo: sumber paket perangkat lunak.

---

## Referensi lanjutan

**Dasar Linux dan CLI**

* [The Linux Command Line](https://linuxcommand.org/tlcl.php)
* [Linux Journey](https://linuxjourney.com)
* [GNU Coreutils Manual](https://www.gnu.org/software/coreutils/manual/)

**Bash dan scripting**

* [Bash Reference Manual](https://www.gnu.org/software/bash/manual/)
* [ShellCheck](https://www.shellcheck.net)
* [Bash Hackers Wiki](http://wiki.bash-hackers.org/)

**Systemd dan layanan**

* [systemd Documentation](https://www.freedesktop.org/software/systemd/man/)

**Jaringan Linux**

* [iproute2 Guide](https://wiki.linuxfoundation.org/networking/iproute2)
* [Wireshark User Guide](https://www.wireshark.org/docs/)

**Keamanan**

* [nftables Wiki](https://wiki.nftables.org)
* [SELinux Project](https://selinuxproject.org)
* [AppArmor Docs](https://wiki.ubuntu.com/AppArmor)

---

## Kontribusi

* Fork repository ini.
* Buat branch fitur terpisah.
* Gunakan commit message yang jelas.
* Ajukan pull request ringkas.

---

[⬆️ Kembali ke atas](#modul-03-linux-dasar)

```
```
