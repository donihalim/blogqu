---
draft: false
date: 2019-12-26T23:54:47+07:00
title: "Cara Mencetak Sertifikat PDF Dengan Inkscape-Merge"
subtitle: "Generate sertifikat PDF dengan mudah dan cepat"
seotitle: "Cara mencetak sertifikat PDF dengan inkscape merge di gnu/linux"
description : "Ternyata dengan Inkscape Merge mencetak sertifikat jadi lebih mudah, mari simak tutorialnya."
slug: ""
categories:
- inkscape
- dokumen
resources:
- src: "cover.jpeg"
  name: "cover"
- src: "*.jpeg"
---

Bismillahirrohmanirrohim.

Dengan Inkscape merge mencetak sertifikat lebih cepat dan effisien. Berbekal aplikasi inkscape untuk generate pdf, libreoffice calc untuk membuat data spreadsheet csv, dan terminal emulator tentunya.
***

## Pasang Inkscape Merge

Buka terminal anda kemudian jalankan perintah ini

```
gem install inkscape_merge
```
{{< photo src="install-inkscape-merge.png" alt="install-inkscape-merge" >}}

Jika gem path muncul peringatan seperti diatas, maka tambahkan baris berikut untuk ditambahkan ke .bashrc, .zshrc atau shell anda lainnya.

```
# gem path
export PATH="${HOME}/.gem/ruby/2.6.0/bin:$PATH"
```

{{< photo src="gem-path.jpeg" alt="gem-path" >}}

***
## Variabel

Pada tutorial ini Saya akan menggunakan variabel seperti berikut.

* %VAR_nomer%
* %VAR_nama%
* %VAR_status%

Variabel ini hanya sekedar contoh, Anda bisa menggunakan variabel lain misalnya id, inisial, alamat, hp, instansi dan lain-lain. Jadi, untuk membuat variabel diawali dengan %VAR_ kemudian diakhiri dengan %.

***
## Membuat Template Sertifikat dengan Inkscape

Tahap ini membuat template dengan Inkscape. Buatlah sertifikat dengan ukuran A4 format datar (lebar=29.7, tinggi=21 cm). Sebagai contoh hasil template.svg seperti berikut ini.

{{< photo src="contoh-sertifikat.jpeg" alt="contoh-sertifikat" >}}

Perhatikan juga setiap variabelnya.

{{< photo src="variabel-sertifikat.jpeg" alt="variabel-sertifikat" >}}

Pastikan menggunakan rata tengah untuk variabel. Umumnya ketika di generate untuk variabel nama kadang tidak lurus.

{{< photoset max="3" >}}
  {{< photo src="tengah-1.jpeg" alt="tengah-1" >}}
  {{< photo src="tengah-2.jpeg" alt="tengah-2" >}}
  {{< photo src="tengah-3.jpeg" alt="tengah-3" >}}
{{</ photoset >}}

***
## Membuat Data CSV

Buka libreoffice calc, kemudian buatlah data seperti ini sebagai contohnya.

{{< photo src="data-sertifikat.jpeg" alt="data-sertifikat" >}}

Pastikan variabel di calc ini memiliki nama yang sesuai dengan variabel di template svg tadi. Kemudian simpan dengan format `.csv`

{{< photo src="simpan-sertifikat.jpeg" alt="simpan-sertifikat" >}}

***
## Eksekusi

Perintah eksekusinya begitu mudah dipahami.

```
inkscape_merge -d [.csv] -f [.svg] -o [hasil.pdf]
```

Sebagai contoh:

```
inkscape_merge -d data.csv -f template.svg -o sertifikat/%VAR_nama%-pelatihan-batch-1.pdf
```

{{< photo src="contoh-perintah.jpeg" alt="contoh-perintah" >}}

Maka keluarannya seperti ini.

{{< photo src="contoh-keluaran.jpeg" alt="contoh-keluaran" >}}

keterangan:
* -d = data csv
* -f = file/berkas template svg
* -o = keluaran sertifikat, pada contoh diatas yaitu membuat direktori sertifikat dan setiap nama berkas sertifikat diawali dengan variabel nama.

***
## Hasil Eksekusi

Hasil PDF berada di direktori "sertifikat"

{{< photo src="contoh-hasil.jpeg" alt="contoh-hasil" >}}

Begitu mudah bukan. Sekian, semoga bermanfaat.

***
## Pranala penting

* Github [inkscape_merge](https://github.com/borgand/inkscape_merge)
* Unduh artboard [sertifikat](https://gitlab.com/hervyqa/artboard/raw/master/sertifikat.svg?inline=false)
***
