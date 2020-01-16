---
title: "Cara Mudah Mengoptimalkan Inkscape"
subtitle: "Meminimalisir Not Responding dan Mempercepat Work Flow"
seotitle: "Mengoptimalkan Inkscape untuk mempercepat Work flow dan Meminimalisir Force Close"
date: 2019-07-27T10:25:48+07:00
draft: false
slug: "cara-mudah-mengoptimalkan-inkscape"
categories:
- inkscape
- desain
tags:
  - inkscape
  - free software
  - ilustrasi
  - pemula
description : "Beberapa ulasan singkat dan menarik untuk mengoptimalkan kinerja inkscape. Tujuannya untuk mempercepat workflow dan meminimalisir terjadinya force close."
resources:
- src: "cover.jpeg"
  name: "cover"
- src: "*.jpeg"
---

Bismillahirrohmanirrohim.

Tips ini penulis gunakan untuk menghindari tutup paksa di inkscape. Terkadang sedikit merepotkan harus membuka berkas SVG-nya lagi ketika ditutup paksa. Tetapi Alhamdullillah ada beberapa tipsnya sederhana yang saya rangkum seperti dibawah ini.

***

## Gunakan filter kualitas rendah

Saya menggunakan settingan ini untuk pengaturan rendering filter. Gunanya untuk mempercepat proses render filter dan blur.

* Pilih **Edit** > **Preferences**.
* Pilih tab **Rendering**.
* Pada bagian **Grassian blur quality for display**, pilih **lowest quality**.
* Pada bagian **Filter effect quality for display**, pilih **lowest quality**.

Jika menggunakan blur, sebaiknya jangan meng-_zoom_ area blur terlalu dekat.

## Gunakan ikon paling kecil

Manfaatnya untuk memaksimalkan layar kanvas dengan mengurangi ukuran ikon.

* Pilih **Edit** > **Preferences**.
* Pilih tab **Interface**.
* Pilih **Toolbox icon size** : **Smaller**.
* Pilih **Control Bar icon size** : **Smaller**.
* Pilih **Secondary Toolbar icon size** : **Smaller**.

## Impor bitmap dengan link

Ketika import gambar bitmap akan ada pilihan untuk mode embed atau linked. Saya sendiri lebih memilih _link_  untuk mengimpor gambar bitmap. Anda juga bisa mengaturnya di bagian preferences.

* Pilih **Edit** > **Preferences**.
* Pilih tab **Bitmaps**.
* Dibagian **Import** hilangkan ceklis **Ask about linking and scaling when importing**.
* Pada **Bitmap link**, pilih: **Link**.
* Pada **Bitmap scale** : **Blocky**.

## Aktifkan autosave

Karena di Windows tidak ada duplikasi ketika _force close_ maka aktifkan juga autosave di preferences.

* Pilih **Edit** > **Preferences**.
* Pilih tab **Input/Output**
* Ceklis **Enable autosave**

Untuk Windows, lokasi direktori autosave diganti dengan nama usernya :

* Autosave directory : **C:\Users\namauser**

Untuk GNU/Linux, tetap seperti ini :

* Autosave directory : **/tmp**

Terima kasih juga kepada [Abu Sahal Wisnu](https://t.me/waditos) yang telah mengkoreksi. :)

## Aktifkan snap seperlunya

Tombol pintasan snap adalah **<kbd>%</kbd>**, letak snap dibagian sebelah kanan toolbox. Ketika Anda bekerja dengan banyak node, saran Penulis cukup mengaktifkan snap seperlunya saja. Misalnya,

* snap to path, node, and handles.
* snap to cusp nodes, incl. rectagle corners.
* snap other points.
* snap to page border.

## Hindari undo/redo mode teks

Ketika anda masih dalam mode teks atau masih mengetikkan kata dan akan melakukan proses undo, maka sebaiknya keluarlah dulu dengan menekan **Esc** kemudian boleh undo dan redo. Biasanya akan not-responding dan akan ditutup paksa. Tetapi ketika desain Anda ringan (logo misalnya) dan tidak banyak node yang ribet maka aman-aman saja pakai undo redo sebanyak apapun.

## Gradasi sedikit node

Penulis sering menggunakan gradasi tapi tidak pernah sampai _force close_. Jika dirasa berat, maka segeralah simpan dan buka kembali berkas inkscape tadi.

## Lingkungan Desktop yang ringan

Khusus pengguna linux, kalau RAM Anda dibawah 2Gib sebaiknya gunakan Lingkungan Desktop yang ringan misalnya Xfce, Lxqt, Openbox, atau migrasi ke Window Manager. Jika Anda migrasi ke Window Manager (WM) cara ini terbilang optimalisasi yang ekstrim, karena membutuhkan learning curve yang tinggi.

***

Jadi, itu saja beberapa hal yang harus dilakukan dan harus dihindari. Sekian, terima kasih sudah membaca. Semoga bermanfaat. :)

[Inkscape]:https://www.inkscape.org
[Gimp]:https://www.gimp.org

[GNOME.ID]:https://www.gnome.id
[BUKU CC-ID]:https://bit.ly/madewithccID
[Wikimedia]:https://www.wikkimedia.org/

[Behance]:https://www.b.net
[Dribbble]:https://www.dribbble.com

[AdobeStock]:https//www.stock.adobe.com
[123rf]:https//www.123rf.com
[Freepik]:https//www.freepik.com
[Dreamstime]:https//www.dreamstime.com
[Shutterstock]:https//www.shutterstock.com
