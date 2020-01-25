---
draft: false
date: 2020-01-25T02:25:10Z
title: "Bluetooth Tetap Aktif Saat Mode Pesawat Di Android 11"
subtitle: "Fitur baru mode pesawat yang akan datang di android 11"
seotitle: "Bluetooth Tetap Aktif Saat Mode Pesawat Di Android 11"
description : "Fitur baru android 11 yang mana saat mengakitfkan mode pesawat, bluetooth tidak ikut mati."
slug: ""
categories:
- android
resources:
- src: "cover.jpeg"
  name: "cover"
- src: "*.jpeg"
---

**Sampurasun**. Mode pesawat merupakan sebuah fitur dari Android yang sudah lama ada. Yang mana berfungsi untuk
mematikan wireless radio seperti WiFi, Data Seluler dan Bluetooth. Pada Android 11 yang akan datang, mode pesawat
akan menjadi lebih _pintar_ lagi.

***

Sebuah _commit_ dari Gerrit AOSP yang berjudul **"Context-aware Bluetooth airplane mode"** meminta Google untuk
mengubah fungsi dari mode pesawat di Android 11 untuk tidak mematikan Bluetooth saat Anda sedang melakukan
_streaming_ audio lewat Bluetooth.


Berikut isi pesan [commit](https://android-review.googlesource.com/c/platform/frameworks/base/+/1179105) tersebut :

> Do not automatically turn off Bluetooth when airplane mode is turned on and Bluetooth is in one of the following
situations:
>1. Bluetooth A2DP is connected.
>2. Bluetooth Hearing Aid profile is connected.

Feature-request ini sudah ter-merge, artinya Anda akan mendapatkan fitur ini pada rilis Android 11 yang akan datang.

***

Jadi bagaimana menurut anda tentang perubahan fungsi dari mode pesawat ini ? Tuliskan opini Anda di kolom
komentar. Hatur Nuhun.

***

Referensi : [Xda
Developers](https://www.xda-developers.com/airplane-mode-stop-shutting-down-bluetooth-audio-android-11-r/?fbclid=IwAR2ZxuDQCzI3jhViuyRlSnlq8EP7uTSLWHMf1NBfnX5tfZClevy7s-iJ6uk)
