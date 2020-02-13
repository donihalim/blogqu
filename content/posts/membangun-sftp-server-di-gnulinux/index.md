---
draft: true
date: 2020-02-13T02:08:33Z
title: "Membangun SFTP Server Di GNU/Linux"
subtitle: "Berbagi berkas lebih mudah dan aman menggunakan SFTP."
seotitle: "Membangun SFTP Server Di GNU/Linux"
description : "Berbagi berkas antar server lebih mudah dan aman menggunakan SFTP."
slug: ""
categories:
- linux
- raspberrypi
resources:
- src: "cover.jpeg"
  name: "cover"
- src: "*.jpeg"
---

Sampurasun. Bagi Anda yang sudah cukup lama menggunakan GNU/Linux pastinya sudah tidak asing lagi
dengan FTP(File Transfer Protocol) sebuah metode yang paling umum digunakan untuk
berbagi(download/upload) berkas
antar server atau client ke server. 

Namun karena alasan keamanan, FTP mulai ditinggalkan dan mulai beralih ke
SFTP. Sebelum lanjut ke pokok pembahasan, penulis akan menjelaskan terlebih dahulu mengenai apa itu SFTP secara
singkat.

## **Apa Itu SFTP ?**
SFTP merupakan kependekan dari _SSH File Transfer Protocol_ atau juga dikenal dengan _Secure File Transfer
Protocol_, sebuah "versi lanjutan" dari FTP yang berjalan di atas protocol SSH. Layanan ini memungkinkan
pengguna untuk berbagi berkas dengan lebih mudah dan aman melalui koneksi yang ter-enkripsi. Sama halnya
dengan FTP, hanya saja koneksi yang dibawa oleh FTP tidak ter-enkripsi sehingga lebih rentan dalam segi
keamanan.

Anda dapat menemukan penjelasan lebih lengkap mengenai SFTP di Internet. Selanjutnya penulis akan
menjelaskan bagaimana cara membangun SFTP server di GNU/Linux.

***


{{< photo src=".jpeg" alt="" >}}

{{< photo class=fullwidth src=".jpeg" alt="" >}}

{{< photoset max="2" >}}
  {{< photo src=".jpeg" alt="" >}}
  {{< photo src=".jpeg" alt="" >}}
{{</ photoset >}}

{{< photoset max="3" >}}
  {{< photo src=".jpeg" alt="" >}}
  {{< photo src=".jpeg" alt="" >}}
  {{< photo src=".jpeg" alt="" >}}
{{</ photoset >}}


***
