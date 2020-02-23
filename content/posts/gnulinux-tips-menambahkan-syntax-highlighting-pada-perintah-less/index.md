---
draft: false
date: 2020-02-23T11:24:06Z
title: "GNU/Linux Tips: Menambahkan Syntax Highlighting Pada Perintah Less"
subtitle: "Buat perintah less lebih berwarna dengan syntax highlighting"
seotitle: "GNU/Linux Tips: Menambahkan Syntax Highlighting Pada Perintah Less"
description : "Tulisan ini menjelaskan cara menambahkan syntax highlighting pada perintah less menggunakan sebuah
perangkat lunak bebas bernama source-highlight, sebuah perangkat lunak bebas yang dikembangkan oleh proyek GNU."
slug: "syntax-highlighting-perintah-less"
tags:
- less
- perintah
- terminal
- linux
- GNU
- commands
categories:
- linux
- raspberrypi
resources:
- src: "cover.jpeg"
  name: "cover"
- src: "*.jpeg"
---


Sampurasun.

Jika Anda sering bekerja dengan terminal, pastinya sudah tidak asing lagi dengan `less`, sebuah perintah yang biasa
digunakan untuk melihat konten dari sebuah atau kumpulan berkas.
Hanya saja pada kebanyakan distribusi GNU/Linux, less masih belum terkonfigurasi secara default untuk mendukung syntax
highlighting.

Untungnya bagi pengguna GNU/Linux, ada sebuah perangkat lunak bebas bernama [source-highlight](https://www.gnu.org/software/src-highlite/) yang dikembangkan oleh Proyek [GNU](https://www.gnu.org), program inilah yang nantinya berperan untuk memberikan syntax highlighting dari output perintah less.
Untuk penjelasan lebih lanjut, silahkan kunjungi online man page source-highlight disini:
[man](https://www.gnu.org/software/src-highlite/source-highlight.html).

***

## Instalasi
Pertama instal paket source-highlight pada distribusi GNU/Linux yang Anda gunakan dengan perintah berikut:

Debian, Ubuntu dan turunan nya :
```
$ sudo apt install source-highlight
```

Fedora GNU/Linux :
```
$ sudo dnf install source-highlight
```

Arch GNU/Linux dan turunan nya :
```
$ sudo pacman -S source-highlight
```

## Konfigurasi
Setelah paket tersebut terinstal, saat nya melakukan komfigurasi untuk perintah less.

Tambahkan baris berikut ke dalam file **~/.profile** jika Anda menggunakan _bash_ atau **~/.zprofile** jika Anda
menggunakan _zsh_ sebagai default shell :
```
export LESSOPEN="| /usr/share/source-highlight/src-hilite-lesspipe.sh %s"
export LESS=' -R'
```
Reload profile shell Anda :
```
# Bash
$ source ~/.profile

# Zsh
$ source ~/.zprofile
```
{{< photo src="profile.png" alt="Konfigurasi Profile" >}}

Berikut perbandingan perintah `less` tanpa dan menggunakan syntax highlighting:


{{< photoset max="2" >}}
  {{< photo src="nosyntax.png" alt="Output Tanpa Syntax Highlighting" >}}
  {{< photo src="wsyntax.png" alt="Output Menggunakan Syntax Highlighting" >}}
{{</ photoset >}}

## Penutup
Itu saja untuk GNU/Linux Tips kali ini, semoga tulisan ini dapat berguna dan bermanfaat bagi Anda. Jika Anda memiliki
pertanyaan, silahkan gunakan kolom komentar di bawah.

Hatur Nuhun.

***
