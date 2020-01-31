---
draft: false
date: 2020-01-31T04:44:39Z
title: "Hal Yang Perlu Dilakukan Setelah Menginstal Fedora"
subtitle: "Selesai menginstal Fedora? Selanjutnya apa?"
seotitle: "Hal Yang Perlu Dilakukan Setelah Menginstal Fedora"
description : "Selesai Menginstal Fedora? Selanjutnya Apa?"
slug: ""
categories:
- linux
resources:
- src: "cover.jpeg"
  name: "cover"
- src: "*.jpeg"
---

Sampurasun. Pada kesempatan ini Penulis akan membagikan hal-hal dasar yang perlu dilakukan
setelah menginstal Fedora GNU/Linux. Disini Penulis akan mejelaskan prosedur pembaruan sistem
awal(System Update), menambahkan _third-party_ repository untuk mendapatkan lebih banyak
_software_, dan lain nya.


Sebelum mengikuti panduan ini, pastikan komputer Anda terhubung dengan koneksi internet. Hal ini
diperlukan karena Anda akan mengunduh paket-paket yang diperlukan dari server. Baiklah, kita lanjutkan.

***

## **1. Melakukan Update Sistem**

Melakukan update sistem merupakan hal dasar yang biasa dilakukan setelah pertama kali menginstal sistem operasi GNU/Linux.
Terlepas dari _distribusi_ apapun yang Anda gunakan.

Untuk mengupdate sistem, jalankan perintah berikut :
```
$ sudo dnf update
```
Proses ini akan memakan waktu, tergantung kecepatan internet dan spesifikasi
komputer Anda.

Setelah proses update selesai pertimbangkan melakukan **reboot**, terutama jika _kernel_ dan
_driver_ yang terinstal ikut terupdate.

## **2. Mengubah Hostname**

Dikarenakan tidak adanya opsi untuk mengubah _hostname_ pada saat proses instalasi Fedora GNU/Linux,
maka Anda perlu mengubahnya secara manual. Pertama kali selesai menginstal Fedora GNU/Linux, hostname yang
diberikan oleh sistem adalah _localhost_. 

Untuk mengubah hostname, jalankan perintah berikut:
```
$ sudo hostnamectl set-hostname --static hostname-anda
```
**Note** : Reboot diperlukan.

## **3. Menambahkan Repository RPM Fusion**

**RPM Fusion** adalah repository _pihak ketiga_ yang menawarkan berbagai perangkat lunak **free** dan **non-free** yang tidak
disediakan oleh repository resmi Fedora GNU/Linux.

Untuk menambahkan repository RPMFusion, jalankan perintah berikut :

**Free**
```
$ sudo dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm
```

**Non-free**
```
$ sudo dnf install https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
```
Untuk melihat repository pihak ketiga lain nya, kunjungi:
[RPMFusion](https://rpmfusion.org/FedoraThirdPartyRepos)

## **4. Mengakfikan Plugin DeltaRPM dan Fastest Mirror**
Alih-alih mengunduh paket lengkap untuk perubahan kecil saat melakukan update pada paket tertentu,
**DeltaRPM** memungkinkan Anda untuk hanya mengunduh perubahan yang terjadi pada paket tersebut saja.
Contohnya jika Anda mengupdate Firefox(54) ke Firefox(55), Anda hanya akan mengunduh
perubahan-perubahan yang terjadi dari v.54 dan v.55. Hal ini dapat menghemat _bandwidth_ saat Anda
melakukan update.

Sedangkan dengan **Fastest Mirror**, sistem akan menentukan server terdekat dengan lokasi Anda saat akan
mengunduh paket menggunakan **DNF**. Artinya jika Anda berada di Indonesia, daripada mengunduh paket dari server
US, **DNF** akan mencari server terdekat dengan lokasi Anda sehingga memungkinkan proses unduhan lebih cepat.

Untuk mengaktifkan plugin DeltaRPM dan Fastest Mirror, tambahkan baris di bawah ini kedalam file
`/etc/dnf/dnf.conf` :

```
deltarpm=True
fastestmirror=True
```

## **5. Mengganti Lingkungan Desktop**
Jika Anda kurang menyukai GNOME atau merasa bahwa lingkungan desktop tersebut terlalu berat, Anda dapat
menggantinya dengan lingkungan desktop lain nya. Berikut beberapa lingkungan desktop yang dapat
menjadi opsi untuk menggantikan GNOME.

### KDE Desktop
Instal KDE Desktop :
```
$ sudo dnf install @kde-desktop
```

### Mate Desktop
Instal Mate Desktop :
```
$ sudo dnf install @mate-desktop
```

### Cinnamon Desktop
Instal Cinnamon Desktop :
```
$ sudo dnf install @cinnamon-desktop
```

### XFCE Desktop
Instal XFCE Desktop :
```
$ sudo dnf install @xfce-desktop
```

### LXDE Desktop
Instal LXDE Desktop :
```
$ sudo dnf install @lxde-desktop
```

***

Itulah beberapa hal yang perlu Anda lakukan setelah pertama kali menginstal Fedora GNU/Linux. Jika Anda
meliki pertanyaan atau saran, silahkan berikan komentar melalui kolom di bawah. Terima Kasih.
