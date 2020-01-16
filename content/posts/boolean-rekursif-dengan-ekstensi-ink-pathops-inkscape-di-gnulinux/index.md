---
draft: false
date: 2019-09-19T11:15:16+07:00
title: "Boolean Rekursif dengan Ekstensi Ink-Pathops Inkscape Di GNU/Linux"
subtitle: "Ekstensi untuk Seamless Pattern"
seotitle: "Boolean Rekursif dengan Ekstensi Ink-Pathops Inkscape Di GNU/Linux"
description : "Ekstensi Inkscape yang berfungsi melakukan operasi boolean seperti union, difference, intersection, exclusion, division, cut path, dan combine secara rekursif dalam waktu yang bersamaan. Ink-pathops juga bisa melakukan proses boolean dalam grup objek."
slug: "boolean-rekursif-dengan-ekstensi-ink-pathops-inkscape-di-gnulinux"
categories:
- inkscape
- desain
resources:
- src: "cover.jpeg"
  name: "cover"
- src: "*.jpeg"
---

<div>{{< youtube G_qMMniCZgw >}}</div>

Bismillahirrohmanirrohim.

Ekstensi Ink-Pathops berfungsi untuk melakukan proses boolean secara bersamaan, baik objek secara individu maupun grup. Biasanya orang kalau melakukan proses boolean seperti union, difference, intersection, exclusion, division, cut path, atau combine pasti melakukannya secara satu-satu. Jika objek tergabung didalam grup maka harus dipisah dulu agar bisa melakukan proses boolean. Namun dengan Ink-pathops orang bisa melakukannya dengan sekali klik untuk multi boolean.

***

Manfaat lain untuk menginstall ekstensi ink-pathops yaitu untuk memotong bagian luar (intersection) objek pattern sesuai artboard yang penulis buat.

Misalnya ketika membuat pattern. Pattern akan sulit dipotong jika manual intersection, tanpa ekstensi. Ketika menggunakan ekstensi proses intersection akan lebih cepat.

Beberapa objek yang dapat di boolean diantaranya seperti :

- Path (segala objek yang dibuat dengan bezier)
- Shape (lingkaran, persegi, dan bintang)
- Teks

Jika terdapat objek hasil clone dan gambar bitmap, maka pathops akan melewatinya.

Lebih jelasnya seperti gambar dibawah ini. Pattern yang belum dipotong dari bagian luar artboard.
{{< photo src="ink-pathops-sebelum.jpeg" alt="ink-pathops-sebelum" >}}

Pattern sudah dipotong dari bagian luar artboard.
{{< photo src="ink-pathops-sesudah.jpeg" alt="ink-pathops-sesudah" >}}

Pada tahap ini pattern sudah siap untuk dijadikan desain seamless pattern.

***

## Tahap Pemasangan

Cara pemasangan ekstensi ini mudah dan cepat, seperti cara dibawah ini.

Langkah 1: Unduh Zip Ink-Pathops pada link [ini].
{{< photo src="1.jpeg" alt="unduh-ink-pathops" >}}

Langkah 2: Ekstrak zip ekstensi.
{{< photo src="2.jpeg" alt="ekstrak-ink-pathops" >}}

Langkah 3: Selanjutnya masuk ke direktori "ink-pathops-v.04 > src", Pilih semua berkas dan salinlah.
{{< photo src="3.jpeg" alt="salin-ink-pathops" >}}

Langkah 4: Tampilkan direktori tersembunyi dengan "CTRL+H" atau "ALT + ," Kemudian masuklah ke direktori ".config".
{{< photo src="4.jpeg" alt="tampilkan-direktori" >}}

Langkah 5: Masuk ke direktori ".config > inkscape > ekstension", kemudian tempelkanlah pada direktori ekstensi tersebut.
{{< photo src="5.jpeg" alt="tempel-ink-pathops" >}}

Langkah 6: Lanjutlah untuk membuka aplikasi Inkscape.
{{< photo src="6.jpeg" alt="buka-inkscape" >}}

Langkah 7: Ink-pathops akan terlihat di Menu Extensions > Generate from Path > PathOps.
{{< photo src="7.jpeg" alt="ekstensi-ink-pathops" >}}

## Penggunaan

Buka menu Pathops :

> **Extensions > Generate from Path > PathOps**

Kemudian pilih boolean akan digunakan.

- Union
- Difference
- Intersection
- Exclusion
- Division
- Cut Path
- Combine

Prosesnya sama dengan boolean inkscape pada umumnya, tinggal memilih objek yang akan digunakan kemudian pilih boolean di PathOps.

## Kode Sumber

Ekstensi ini dikembangkan dan dikelola oleh:
https://gitlab.com/su-v/inx-pathops

Arsip ZIP terbaru bisa di unduh disini: 
https://gitlab.com/su-v/inx-pathops/tags

## Lisensi

Ink-PathOps menggunakan lisensi GPL-2+.

Sekian, tips ekstensi ink-patops kali ini. _Semoga bermanfaat._

***

[ini]:https://gitlab.com/su-v/inx-pathops/tags
