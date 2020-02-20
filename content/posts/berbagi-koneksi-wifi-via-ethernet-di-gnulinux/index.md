---
draft: false
date: 2020-02-16T08:54:06+07:00
title: "Berbagi Koneksi Wi-Fi Melalui Ethernet Di GNU/Linux"
subtitle: "Mudah berbagi koneksi internet di GNU/Linux."
seotitle: "Berbagi Koneksi Wi-Fi Melalui Ethernet Di GNU/Linux"
description : "Konfigurasi NetworkManager untuk berbagi koneksi internet di GNU/Linux."
slug: "berbagi-koneksi-wi-fi-melalui-ethernet-di-gnulinux"
categories:
- linux
resources:
- src: "cover.jpeg"
  name: "cover"
- src: "*.jpeg"
---


Sampurasun. Beberapa waktu lalu saya memiliki masalah untuk mengkoneksikan internet ke perangkat Raspberry Pi, dikarenakan versi Raspberry Pi yang saya miliki terbilang cukup jadul (Raspberry Pi 1B) yang mana tidak memiliki _built-in_ wifi. Tentu saya dapat mengkoneksikan internet melalui USB-Tethring, namun nantinya akan timbul masalah ketika saya ingin mengakses perangkat tersebut secara remote menggunakan laptop.

Lalu saya menemukan alternatif lain, yaitu dengan cara membagikan koneksi internet dari laptop yang terinstal GNU/Linux melalui ethernet yang mana caranya akan saya jelaskan pada tulisan ini.

Ada **dua** cara untuk melakukan hal tersebut, yaitu melalui **GUI** dan **Console**.

***

## 1. GUI
Cara ini dapat Anda lakukan jika GNU/Linux yang terinstal memiliki lingkungan desktop.

Pertama buka terminal dan jalankan perintah berikut :
```
$ nm-connection-editor
```
Maka akan muncul jendela baru seperti berikut ini :
{{< photo src="nm1.png" alt="NetworkManager" >}}

Pada jendela tersebut klik tanda "**+**" lalu pilih **Ethernet** dan klik **Create**.
{{< photo src="nm2.png" alt="Membuat Interface Baru" >}}

Maka akan muncul jendela baru lagi untuk melakukan konfigurasi. Setelah itu klik pada tab **IPv4 Settings**.

Pada bagian **Connection Name** beri nama sesuai keinginan Anda, dan pada bagian **Method** pilih ***Shared to other computers***.
{{< photo src="nm3.png" alt="Konfigurasi Interface Baru" >}}

Simpan hasil konfigurasi tersebut dengan meng-klik tombol **save**. Setelah itu sambungkan kedua perangkat dengan kabel LAN. Maka perangkat yang Anda sambungkan dengan laptop akan otomatis terkoneksi dengan internet.

## 2. Console
Seperti yang saya sebutkan di atas, selain melalui GUI, Anda juga dapat melakukan nya pada Console. Hal ini dilakukan jika GNU/Linux yang terinstal tidak memiliki lingkungan desktop.

Pada console, jalankan perintah berikut :
```
$ nmtui
```
Maka akan muncul tampilan nmtui seperti berikut ini:
{{< photo src="nmtui1.png" alt="NMTUI" >}}

Pilih **Edit a connection** maka akan muncul menu baru seperti berikut ini :
{{< photo src="nmtui2-1.png" alt="Membuat Koneksi Baru NMTUI" >}}

Setelah itu pilih **< Add >** kemudian pilih **Ethernet**.
{{< photo src="nmtui2-2.png" alt="Menambahkan Interface Baru NMTUI" >}}

Pada bagian **Profile name** beri nama sesuai keinginan Anda, dan pada bagian **IPv4 CONFIGURATIONS** pilih ***Shared***. Biarkan bagian lain nya tetap default.
{{< photo src="nmtui3.png" alt="Konfigurasi Interface Baru NMTUI" >}}

Simpan hasil konfigurasi tersebut dengan memilih opsi **< OK >**. Keluar dari nmtui dengan menekan tombol **ESC** pada keyboard beberapa kali.
Setelah itu sambungkan kedua perangkat dengan kabel LAN. Maka perangkat yang Anda sambungkan dengan laptop akan otomatis terkoneksi dengan internet.

***

Itulah cara berbagi koneksi wifi melalui ethernet di GNU/Linux. Jika dirasa ada yang kurang atau
Anda memiliki masukan, silahkan berikan komentar melalui kolom di bawah.

Hatur nuhun.
