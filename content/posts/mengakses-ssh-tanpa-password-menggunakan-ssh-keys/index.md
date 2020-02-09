---
draft: true
date: 2020-02-09T10:31:21Z
title: "Mengakses SSH Tanpa Password Menggunakan SSH Keys"
subtitle: "Login SSH lebih aman menggunakan public-key SSH di GNU/Linux."
seotitle: "Mengakses SSH Tanpa Password Menggunakan SSH Keys"
description : "Login SSH Lebih Aman Menggunakan SSH Keys."
slug: ""
categories:
- linux
- raspberrypi
resources:
- src: "cover.jpeg"
  name: "cover"
- src: "*.jpeg"
---

Sampurasun. SSH atau _Secure Shell_ merupakan sebuah protokol yang paling umum digunakan untuk mengkases
GNU/Linux server secara _remot_. Dengan menggunakan SSH keys Anda tidak perlu lagi menginput
password setiap kali melakukan login ke server. Selain itu, metode ini juga diklaim lebih aman dari pada
menggunakan password atau passphrase.

## **Sebelum Anda Mulai**
Perlu di ingat bahwa mengakses SSH tanpa password disini bukan semata-mata Anda login ke server tanpa password
sama sekali. Anda tetap memerlukan password untuk login ke server yang nantinya digunakan untuk menyalin
_public-key_ yang akan Anda buat di komputer lokal ke dalam server.

***

## **Penjelasan**
Disini Anda akan menggunakan perintah **ssh-keygen** untuk membuat SSH Keys yang mana nantinya akan
terbuat dua file baru di dalam direkori `~/.ssh` dengan nama **"id_rsa"** dan **"id_rsa.pub"**.

- **id_rsa** merupakan private-key yang harus tetap rahasia, hanya Anda yang boleh menggunakan ini.
    Jangan membagikan konten dari file ini pada siapapun.

- **id_rsa.pub** merupakan public-key yang nantinya akan digunakan untuk login ke server. Anda
    bebas membagikan konten dari file ini untuk keperluan tertentu.

Selanjutnya Anda dapat membuat kedua keys tersebut dengan mengikuti langkah-langkah dibawah ini.

## **Membuat SSH Keys**
Untuk mengbuat private-key dan public-key, jalankan perintah berikut di komputer lokal yang akan Anda
gunakan untuk mengakses server :
```
$ ssh-keygen -t rsa -b 4096
```
Lalu akan mucul output seperti ini :
```
Generating public/private rsa key pair.
Enter file in which to save the key (/home/useranda/.ssh/id_rsa):
```
Prompt ini memungkinkan Anda untuk memilih lokasi penyimpanan private-key. Tekan **ENTER** untuk memilih
penyimpanan default yang mana akan tersimpan di direktori tersembunyi **.ssh** di direktori home user Anda. 

```
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
```
Prompt selanjutnya memungkinkan Anda untuk memberikan password pada private-key. Secara default, Anda
akan diminta memasukan password setiap kali menggunakan key tersebut. Anda juga dapat membiarkannya
kosong dengan menekan **ENTER**.

## **Menyalin Public-Key SSH ke Server**
Selanjutnya untuk mengakses server menggunakan public-key yang telah Anda buat, Anda harus menyalin nya
terlebih daluhu dari komputer lokal ke server.

Gunakan perintah `ssh-copy-id` untuk menyalin public-key dari komputer lokal ke server :
```
$ ssh-copy-id user@server -p (port)
```
{{< photo src="" alt="Menyalin Public Key" >}}

## **Mencoba Login ke Server Tanpa Password**
Setelah menyalin public-key ke server, seharusnya saat ini Anda sudah dapat login ke server tanpa menginput password.
```
$ ssh user@server -p (port)
```
{{< photo src="" alt="Login Tanpa Password" >}}

***
