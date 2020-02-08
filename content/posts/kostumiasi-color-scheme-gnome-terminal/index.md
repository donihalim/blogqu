---
draft: false
date: 2020-02-08T14:00:37+07:00
title: "Kostumisasi Color Scheme GNOME Terminal"
subtitle: "Kumpulan Color Scheme GNOME Terminal"
seotitle: "Kostumisasi Color Scheme GNOME Terminal"
description : "Mengkostumisasi Skema Warna GNOME Terminal"
slug: "kostumisasi-color-scheme-gnome-terminal"
categories:
- linux
- aplikasi
resources:
- src: "cover.jpeg"
  name: "cover"
- src: "*.jpeg"
---

Sampurasun. Bagi Anda yang menghabisakan banyak waktu bekerja di depan terminal pastinya ingin membuat tampilan terminal yang Anda gunakan menjadi senyaman mungkin sehingga dapat membantu Anda untuk tetap fokus terhadap apa yang sedang dikerjakan.

Pada tulisan ini Penulis akan membagikan kumpulan color scheme untuk GNOME Terminal dari sebuah repository Github bernama [Gogh](https://github.com/Mayccoll/Gogh) yang mana berisi kumpulan-kumpulan color scheme yang sangat menarik.

***

## **Pre-Install**
Seperti yang disebutkan pada bagian [instalasi](https://github.com/Mayccoll/Gogh?files=1#pre-install) di laman Github Gogh, Anda diharuskan menginstal paket yang diperlukan untuk menjalankan script tersebut. Buka terminal lalu jalankan perintah berikut:
```
$ sudo apt-get install dconf-cli uuid-runtime
```

## **Menginstal dan Memilih Color Scheme**
Untuk menginstal color scheme yang tersedia, Anda cukup menjalankan satu baris perintah di terminal.
```
$  bash -c  "$(wget -qO- https://git.io/vQgMr)"
```

Maka Anda akan disuguhi pilihan color scheme mana yang ingin Anda instal.

{{< photoset max="2" >}}
  {{< photo src="gogh-1.png" alt="Pilihan Warna" >}}
  {{< photo src="gogh-2.png" alt="Pilihan Warna 2" >}}
{{</ photoset >}}

Untuk melihat cuplikan color scheme yang tersedia, Anda dapat mengunjungi [laman Gogh](https://mayccoll.github.io/Gogh/).

{{< photo src="pilihan-warna.png" alt="Laman Gogh" >}}

Setelah menginstal color scheme yang Anda pilih, _klik kanan_ pada layar terminal lalu arahkan mouse pointer ke menu **Profiles**, maka Anda akan melihat profile baru dengan nama sesuai dengan color scheme yang sebelumnya Anda instal.

{{< photoset max="2" >}}
  {{< photo src="profile-baru.png" alt="Profile Baru" >}}
  {{< photo src="warna-baru.png" alt="Contoh Warna Baru" >}}
{{</ photoset >}}

Untuk menginstal color scheme lain nya, ulangi kembali langkah di atas.

***

Sekian dari Penulis, semoga tulisan ini dapat bermanfaat bagi Anda dan terima kasih telah menyempatkan waktu untuk membaca tulisan ini. Jika dirasa ada yang kurang atau Anda memiliki kritik dan saran silahkan berikan komentar melalui kolom di bawah. Hatur nuhun.