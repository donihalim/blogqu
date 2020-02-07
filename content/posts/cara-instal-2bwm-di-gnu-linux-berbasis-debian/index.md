---
draft: true
date: 2020-02-07T05:02:12Z
title: "Cara Instal 2bwm Di GNU/Linux Berbasis Debian"
subtitle: "2bwm: A fast floating window manager."
seotitle: "Cara instal 2bwm Di GNU/Linux Berbasi Debian"
description : "2bwm: A fast floating window manager."
slug: ""
categories:
- linux
- raspberrypi
- desktop
resources:
- src: "cover.jpeg"
  name: "cover"
- src: "*.jpeg"
---

Sampurasun. Pada kesempatan ini Penulis akan membagikan tutorial cara menginstal 2bwm di GNU/Linux
berbasis Debian. 2bwm adalah salah satu ***floating window manager*** yang ditulis di atas _XCB library_
yang berasal dari _mwcwm_. Di dalam 2bwm semuanya dapat di akses melalui keyboard, mulai dari
memperbesar, memperkecil dan memindahkan jendela aplikasi.

Untuk penjelasan lebih detail, kunjungin laman [Github](https://github.com/venam/2bwm) 2bwm.

***

## **1. Menginstal Library Yang Dibutuhkan**
Untuk menginstal XCB library yang dibutuhkan, buka terminal dan jalankan perintah berikut:
```
sudo apt-get install libxcb-randr0-dev \
libxcb-ewmh-dev \
libxcb-icccm4-dev \
libxcb-keysyms1-dev \
libxcb-xrm-dev
```

**Tambahan**: Instal beberapa aplikasi tambahan untuk menjalankan 2bwm. Jalankan perintah berikut:
```
sudo apt-get install rxvt-unicode \
lemonbar \
dmenu
```

## **2. Menginstal dan Mengkonfigurasi 2bwm**
Untuk mengkompilasi 2bwm dari _source_ pertama Anda harus mengunduh terlebih dahulu kode sumber dari 2bwm.
Untuk mengunduh versi terbaru dari 2bwm jalankan perintah berikut:
```
git clone git://github.com/venam/2bwm.git
```
Sebelum melakukan proses kompilasi, Anda harus mengkonfigurasi nya terlebih dahulu agar 2bwm dapat
berfungsi.



***
