---
title: "5 Hal yang perlu dilakukan setelah install GNU/Linux KDE Neon"
subtitle: "Sistem Operasi ilustrator"
seotitle: "5 Hal yang perlu dilakukan setelah install GNU/Linux KDE Neon"
description : "Beberapa hal yang perlu dilakukan setelah install KDE NEON. Install pembaruan, aplikasi, dan codec."
date: 2019-09-10T11:43:24+07:00
draft: false
slug: "5-hal-yang-perlu-dilakukan-setelah-install-gnulinux-kde-neon"
categories:
- desktop
resources:
- src: "cover.jpeg"
  name: "cover"
- src: "*.jpeg"
---

Bismillahirrohmanirrohim.

KDE Neon adalah GNU/Linux Distribusi yang minimal dan mudah dikonfigurasi. KDE Neon juga juga dikembangkan oleh KDE Project dan membawa Software KDE terbaru setiap rilisnya. Bagusnya lagi KDE Neon bisa menjalankan dengan LiveCD.

Tulisan ini menunjukkan hal-hal apa saja yang perlu dilakukan setalah install GNU/Linux KDE Neon untuk pengguna pemula.

***

## Refresh dan Update

Ada dua cara mengupdate di GNU/Linux, pertama menggunakan GUI di software center KDE atau yang disebut Dicover dan kedua menggunakan CLI di terminal.
Hal yang penulis sukai adalah mengeksekusi perintah dengan terminal. Di KDE Aplikasi, terminal biasa disebut "Konsole".

Buka aplikasi "Konsole" di menu kemudian masukkan perintah berikut

```
sudo pkcon refresh -y && sudo pkcon update -y
```

***

## Install Paket Dasar

Selanjutnya install paket dasar seperti git, fonta, codec, icc-profil dan lain-lain.

```
sudo pkcon install \
git kio-gdrive bluez-obexd gwenview \
ffmpegthumbs kffmpegthumbnailer usb-creator-kde \
ttf-mscorefonts-installer fonts-font-awesome \
ttf-bitstream-vera testdisk kubuntu-restricted-extras \
kcron kubuntu-driver-manager icc-profiles icc-profiles-free -y
```

***

## Install KDE Aplikasi

Memasang aplikasi QT dan KDE.

```
sudo pkcon install \
kamoso kate kcalc kdeconnect \
partitionmanager kmail kget kdf \
kcolorchooser kfind k3b kaffeine elisa \
amarok sweeper simplescreenrecorder ktorrent akregator \
konversation kleopatra korganizer kontact -y
```

Karena sudah install Kaffeine player sebagai pemutar Video, sebaiknya hapus VLC Sebab Kaffeine lebih ringan dan dikembangkan langsung oleh tim KDE.

```
sudo pkcon install kaffeine -y; sudo pkcon remove vlc -y
```

Jika Anda kurang suka dengan browser Firefox, sebaiknya pasang Falkon sebagai alternatifnya. Falkon juga dikembangkan oleh tim KDE.

```
sudo pkcon install falkon -y; sudo pkcon remove firefox -y;
```

***

## Install Paket Aplikasi untuk Desain dan Produktifitas

Pasang Aplikasi desain dan perkantoran.
```
sudo pkcon install inkscape gimp optipng \
libreoffice libreoffice-kde \
libreoffice-style-breeze ktouch -y
```

Jika Anda seorang pembuat Fonta pasanglah fontforge.
```
sudo pkcon install \
fontforge -y
```

Jika Anda seorang editor video dan animasi pasanglah kdenlive dan synfigstudio.
```
sudo pkcon install \
kdenlive synfigstudio -y 
```

***

## Terakhir Hapus Depedensi yang tidak diperlukan

```
sudo apt autoremove -y
```

Nah, Selesai.

Sekarang sistem operasi KDE NEON sudah siap digunakan untuk sehari-hari. Sekian, semoga bermanfaat.

***
