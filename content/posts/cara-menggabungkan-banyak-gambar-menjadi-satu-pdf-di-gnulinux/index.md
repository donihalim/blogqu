---
draft: false
date: 2020-02-27T22:38:12Z
title: "Cara Menggabungkan Banyak Gambar Menjadi Satu PDF Di GNU/Linux"
subtitle: "Mudah menggabungkan banyak gambar dengan ImageMagick"
seotitle: "Cara Menggabungkan Banyak Gambar Menjadi Satu PDF Di GNU/Linux"
description : "Cara paling mudah menggabungkan banyak gambar menjadi satu berkas PDF di GNU/Linux
menggunakan ImageMagick."
slug: "cara-menggabungkan-gambar-menjadi-satu-pdf-gnulinux"
categories:
- linux
resources:
- src: "cover.jpeg"
  name: "cover"
- src: "*.jpeg"
---

Sampurasun.

Mungkin karena alasan tertentu Anda perlu menggabungkan banyak gambar menjadi satu berkas PDF. Di GNU/Linux
untuk mencapai hal tersebut sangatlah mudah, hanya dengan satu baris _commandline_ saja.

Anda hanya memerlukan satu paket bernama [ImageMagick](https://imagemagick.org/index.php) yang biasanya sudah terinstal secara default
dikebanyakan distro GNU/Linux modern, karena paket tersebut biasanya menjadi depensi paket-paket lain.
***

## Menggabungkan Gambar
Untuk menggabungkan gambar saya akan menggunakan perintah `convert` yang merupakan bawaan dari
ImageMagick.

Sebagai demo, disini saya memiliki satu buah direktori dengan nama **Gambarquh** yang berisi skrinsot yang
cukup penting bagi saya hehe.
```
Gambarquh
├── Screenshot_20200107-075031.png
├── Screenshot_20200107-075040.png
├── Screenshot_20200107-075052.png
├── Screenshot_20200109-050742.png
└── Screenshot_20200111-155136.png
```
Untuk menggabungkan gambar-gambar tersebut menjadi satu pdf, pertama masuk kedalam direktori yang berisi gambar-gambar untuk digabungkan,
lalu jalankan perintah ini,

```
$ convert * namaberkas.pdf
```
>Ganti namaberkas sesuai keinginan Anda.

Tanda (*) berguna untuk meng-include semua gambar yang terdapat pada direktori, untuk menggabungkan hanya
gambar tertentu, gunakan perintah ini,
```
$ convert gambar1.png gambar2.png namaberkas.pdf
```

Lama proses tergantung banyaknya gambar dan ukuran gambar itu sendiri, tunggulah sampai proses selesai,
jika berhasil maka akan ada berkas PDF baru sesuai dengan nama yang Anda berikan pada perintah di atas.

### Penutup
Selain ini, masih banyak fitur-fitur menarik dari ImageMagick yang nantinya akan saya bahas dalam
tulisan selanjutnya. Semoga tips kali ini dapat berguna dan bermanfaat bagi Anda, seperti biasa kritik dan
saran sangat diterima.

Hatur Nuhun.

***
