---
draft: false
date: 2020-01-24T09:25:09+07:00
title: "Panduan Instalasi Arch Linux Secara Offline Di UEFI"
subtitle: "Instalasi Arch Linux Secara Offline Di UEFI"
seotitle: "Panduan Instalasi Arch Linux Secara Offile Di UEFI"
description : "Artikel ini merupakan panduan untuk melakukan instalasi arch linux secara offline di UEFI."
slug: "install-archlinux-offline"
categories:
- linux
resources:
- src: "cover.jpg"
  name: "cover"
- src: "*.jpg"
---

Permasalahan umum yang sering terjadi ketika hendak melakukan instalasi Arch Linux yaitu tidak adanya koneksi internet atau kecepatan internet yang lambat. Selain itu, belum didukung/terinstalnya driver WIFI juga menjadi faktor ***sulitnya*** melakukan instalasi Arch Linux. Namun bagi sebagian orang yang memiliki perangkat Andoid atau internet rumahan, permasalah tersebut dapat diatasi dengan mengkoneksikan internet lewat **USB Tethring** atau kabel **LAN**. Setidaknya itulah pendapat saya.

Pada dasarnya proses instalasi Arch Linux secara offline ini yaitu dengan mengkopi seluruh isi dari file **archiso** ke media yang menjadi target instalasi, misalnya Hard Disk atau Flash Disk. Tentu ada beberapa berkas dan direktori yang nantinya akan dihapus. Biasanya berkas dan direktori tersebut berisikan service atau konfigurasi yang diperlukan untuk menjalankan ***live session*** Arch Linux.

Perlu digarisbawahi bahwa panduan ini ditujukan untuk Anda yang pernah atau sudah berhasil melakukan instalasi Arch Linux secara normal(**baca**: pacstrap) yang mana akan mengunduh paket-paket yang diperlukan kedalam media instalasi.
>Like always, do with your own risk.

## **Menyiapkan Partisi**
Untuk membuat partisi, Anda dapat menggunakan aplikasi perkakas `cgdisk` atau `cfdisk`.
Sebagai contoh, berikut skema partisi yang telah saya buat :
- **/dev/sda1**, 4GB untuk partisi swap
- **/dev/sda2**, 1GB untuk partisi /boot/uefi
- **/dev/sda3**, 20GB untuk partisi / (baca: root)
- **/dev/sda4**, 20GB untuk partisi /home

## **Memformat Partisi**

**PERINGATAN** : ketika hendak melakukan format pada partisi, pastikan kembali partisi tersebut benar-benar partisi yang tepat. Anda tidak ingin kehilangan data-data penting Anda.

Untuk memformat partisi yang telah dibuat, jalankan perintah berikut :
```
mkswap /dev/sda1
mkfs.fat -F 32 /dev/sda2
mkfs.ext4 /dev/sda3 -L "ArchRoot"
mkfs.ext4 /dev/sda4 -L "ArchHome"
```
>Sesuaikan /dev/sdaX dengan partisi yang telah anda buat.

## **Mounting Partisi**
Setelah melakukan format pada ke-4 partisi di atas, kemudian lakukan mounting dan mengaktifkan swap.
>Jika Anda mengikuti skema partisi saya, maka Anda dapat langsung mengkopi perintah dibawah. Namun jika skema partisi Anda berbeda, silahkan disesuaikan.

**PERINGATAN:** periksa kembali partisi yang akan di mount, jangan sampai salah melakukan mounting.

```
swapon /dev/sda1
mount /dev/sda3 /mnt
mkdir /mnt/{boot,home}
mkdir /mnt/boot/efi
mount /dev/sda2 /mnt/boot/efi
mount /dev/sda4 /mnt/home
```
## **Instal archiso Ke Target Instalasi**
Pada langkah ini, jika Anda melaukan intalasi secara normal maka Anda akan menggunakan perintah `pacstrap` yang mana akan mengunduh paket-paket yang diperlukan ke dalam target instalasi. Namun dikarenakan kita melakukan instalasi secara offline, maka kita akan mengkopi keseluruhan isi dari ***archiso***. Jalankan perintah berikut untuk mengkopi keseluruhan isi dari ***archiso*** :

```
cp -ax / /mnt
```
>Opsi (-x) di atas digunakan untuk mencegah beberapa spesial direktori yang tidak seharusnya di kopi kedalam target instalasi.

Setelah itu, kopi kernel image kedalam ***root*** baru :
```
cp -vaT /run/archiso/bootmnt/arch/boot/$(uname -m)/vmlinuz /mnt/boot/vmlinuz-linux
```
## **Generating Fstab**
Mounting partisi yang telah dibuat secara permanen dengan cara memasukan nya kedalam `fstab`.
```
genfstab -U /mnt >> /mnt/etc/fstab
```
Periksa kembali file `/mnt/etc/fstab` untuk memastikan tidak ada kesalahan.

## **Masuk Kedalam Lingkungan Chroot**
Setelah melakukan langkah-langkah diatas, masuk kedalam lingkungan chroot untuk mengkonfigurasi sistem baru.
Jalankan perintah berikut :
```
arch-chroot /mnt /bin/bash
```
>Catatan: Sebelum melakukan panduan Instalasi lainnya, perlu untuk menghilangkan jejak lingkungan Live (dengan kata lain, penyesuaian archiso yang tidak sesuai dengan lingkungan non-Live).

- **Mengembalikan konfigurasi journald**
```
sed -i 's/Storage=volatile/#Storage=auto/' /etc/systemd/journald.conf
```
- **Menghapus speasial rule udev**
```
rm /etc/udev/rules.d/81-dhcpcd.rules
```
- **Mematikan dan menghapus service yang dibuat archiso**
```
systemctl disable pacman-init.service choose-mirror.service
```
```
rm -r /etc/systemd/system/{choose-mirror.service,pacman-init.service,etc-pacman.d-gnupg.mount,getty@tty1.service.d}
```
```
rm /etc/systemd/scripts/choose-mirror
```
- **Menghapus spesial scripts lingkungan live**
```
rm /etc/systemd/system/getty@tty1.service.d/autologin.conf
```
```
rm /root/{.automated_script.sh,.zlogin}
```
```
rm /etc/mkinitcpio-archiso.conf
```
```
rm -r /etc/initcpio
```
- **Import archlinux keys**
```
pacman-key --init
pacman-key --populate archlinux
```
## **Konfigurasi Sistem Baru**
Ketika sudah berada didalam lingkungan chroot sistem baru, maka saatnya melakukan konfigurasi seperti **zona waktu**, **bahasa**, **hostname**, **user**, dan **group**.


## **Mengatur Zona Waktu**

Waktu Indonesia Barat(**WIB**)
```
ln -sf /usr/share/zoneinfo/Asia/Jakarta /etc/localtime
```
Waktu Indonesia Tengah (**WITA**)
```
ln -sf /usr/share/zoneinfo/Asia/Pontianak /etc/localtime
```
Waktu Indonesia Timur (**WIT**)
```
ln -sf /usr/share/zoneinfo/Asia/Jayapura /etc/localtime
```
Setelah memilih zona waktu, jalankan perintah berikut :
```
hwclock --systohc --utc
```
## **Mengatur Locale atau Bahasa**
```
nano /etc/locale.gen
```
Kemudian hilangkan tanda (**#**) pada baris berikut :
```
en_US.UTF-8 UTF-8
id_ID.UTF-8 UTF-8
```
Save dan keluar.

Kemudian jalankan perintah berikut :
```
nano /etc/locale.conf
```
Lalu tambahkan baris berikut :
```
LC_COLLATE=C
LANG=en_US.UTF-8
LC_TIME=id_ID.UTF-8
```
Kemudian jalankan perintah `locale-gen`.

## **Mengatur Hostname**
Untuk membuat file hostname, jalankan perintah berikut:
```
echo nama-anda > /etc/hostname
```

## **Membuat Group dan user**
Untuk membuat group, user dan mengatur password, jalankan perintah berikut :
```
groupadd sudo
useradd -m -g users -G sudo,power,storage user-anda
```
Kemudian edit file `sudoers`.
```
nano /etc/sudoers
```
Carilah baris dibawah ini, lalu hilangkan tanda (**#**).
```
%sudo ALL=(ALL)
```
Save dan keluar.

Untuk mengatur password user, jalankan perintah berikut :
```
passwd user-anda
passwd root
```

## **Initramfs**
Untuk membuat initramfs baru, jalankan perintah berikut :
```
mkinitcpio -P
```

## **Instal GRUB**
Selah melakukan langkah-langkah diatas, saatnya untuk melakukan instalasi GRUB.
```
grub-install /dev/sdX
grub-mkconfig -o /boot/grub/grub.cfg
```
>Perlu di ingat bahwa /dev/**sdX** merupakan disk yang menjadi target instalasi(misalnya, /dev/sda), bukan sub-partisi seperti /dev/sda1.

Sampai disini proses instalasi sudah selesai, Anda dapat keluar dari lingkungan chroot dan melakukan reboot pada sistem. Namun, untuk menghindari hal-hal yang tidak diinginkan sebaiknya melakukan **umount** pada partisi yang sebelumnya telah di **mount**. Dan selamat anda telah berhasil melakukan instalasi Arch Linux secara offline.

## **Penutup**
Sebenarnya tulisan ini saya khususkan untuk menjadi catatan pribadi saja, dikarenakan seringnya saya melakukan proses instal ulang. Namun jika Anda merasa terbantu dengan tulisan ini, saya akan sangat bersyukur.
Mohon maaf jika ada kesalahan-kesalahan dalam penulisan, saat ini saya masih dalam proses pembelajaran dalam menulis.

Jika dirasa ada yang kurang jelas, atau Anda ingin memberi saya masukan, Anda dapat menuliskan komentar dibawah.

Terima Kasih sudah menyempatkan waktu untuk membaca panduan ini, semoga dapat bermanfaat dan membantu bagi Anda.

**Referensi** :
- [Emirar](https://www.emirar.com/2018/03/instal-arch-linux-uefi.html?m=1)
- [Arch Wiki](https://wiki.archlinux.org/index.php/Offline_installation)

