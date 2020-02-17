---
draft: false
date: 2020-02-09T22:12:05Z
title: "Mencegah Koneksi SSH Terputus (Time Out) Di GNU/Linux"
subtitle: "Mengatasi koneksi SSH sering terputus dengan pesan KeepAlive."
seotitle: "Mencegah Koneksi SSH Terputus (Time Out) Di GNU/Linux"
description : "Mengatasi Koneksi SSH Sering Terputus Dengan Opsi KeepAlive"
slug: "mencegah-koneksi-ssh-terputus"
categories:
- linux
- raspberrypi
resources:
- src: "cover.jpeg"
  name: "cover"
- src: "*.jpeg"
---

Sampurasun. Secara default, kebanyakan server SSH diatur untuk memutus koneksi _client_ yang sudah tidak
aktif atau idle setelah beberapa waktu. Anda akan melihat pesan yang kira-kira seperti di bawah ini:
```
Read from remote host server.anda.com: Connection reset by peer
Connection to server.anda.com closed.
```
Untuk mencegah terputus nya koneksi SSH, Anda perlu mengkonfigurasi SSH pada komputer lokal Anda, atau
server yang akan Anda akses.

Sebagai catatan, untuk melakukan konfigurasi pada sisi server, Anda harus memiliki akses admin atau
***superuser***.

***

# Penjelasan
Sebelum Anda mulai, penulis akan menjelaskan dua istilah yang akan digunakan di panduan ini. Dua istilah
tersebut adalah ***sisi client*** dan ***sisi server***.

- Sisi client atau client-side adalah komputer lokal yang akan Anda gunakan untuk login atau mengakses
    server.

- Sisi server atau server-side adalah remote system yang akan Anda akses melalui komputer lokal.

Berikut ini cara melakukan konfigurasi SSH pada kedua sisi (client dan server).

# 1. Sisi client
Cara ini digunakan jika Anda tidak memiliki akses ***superuser*** pada server yang akan Anda akses.

Ada beberapa cara untuk melakukan konfigurasi pada sisi client, berikut akan penulis jelaskan
masing-masing cara tersebut :
### 1a. Global
**Global** artinya jika Anda memiliki lebih dari satu user dalam komputer lokal Anda, maka konfigurasi ini
akan mempengaruhi semua user yang ada.

Buka file `/etc/ssh/ssh_config` dengan editor teks pilihan Anda :
```
$ sudo vim /etc/ssh/ssh_config
```
Lalu tambahkan baris berikut di akhir file :
```
ServerAliveInterval 120
```

### 1b. Single User
**Single User** artinya konfigurasi yang dilakukan hanya akan mempengaruhi **satu** user saja, yaitu
yang sedang Anda gunakan saat ini. User lain dalam komputer Anda tidak akan terpengaruh, karena
konfigurasi ini dilakukan di dalam direktori _home_ user saat ini.

Buat atau ubah file `~/.ssh/config` :
```
$ vim ~/.ssh/config
```
Lalu tambahkan baris berikut ke dalam file config :
```
Host *
ServerAliveInterval 120
```

### 1c. Single User (Manual)
Sama seperti cara single user sebelumnya, cara ini hanya mempengaruhi user yang sedang digunakan saja.
Namun, daripada memasukan nya kedalam file `~/.ssh/config`, Anda akan menambahkan parameter `-o
ServerAliveInterval=<waktu-dalam-detik>` setiap kali menggunakan SSH. Contoh :
```
$ ssh -o ServerAliveInterval=120 user@server_anda -p <port>
```
Daripada menambahkan parameter tersebut setiap kali menggunakan perintah SSH, Anda dapat membuat
***Alliases*** untuk perintah SSH.

Jika Anda menggunakan **BASH**, tambahkan baris berikut ke dalam file `~/.bashrc` :
```
alias ssh='ssh -o ServerAliveInterval=120'
```
Untuk **ZSH**, tambahkan baris berikut ke dalam file `~/.zshrc` :
```
alias ssh='ssh -o ServerAliveInterval=120'
```
Maka untuk mengakses server, Anda hanya perlu menjalankan perintah :
```
$ ssh user@server_anda -p <port>
```
Setelah melakukan konfigurasi pada sisi client dengan salah satu cara di atas, seharusnya saat ini Anda tidak
akan memiliki masalah terputus nya koneksi SSH ketika tidak digunakan. Selanjutnya penulis akan menjelaskan
cara melakukan konfigurasi pada sisi server.

# 2. Sisi Server
Jika Anda melakukan konfigurasi pada sisi client, maka Anda perlu melakukan nya pada
setiap komputer lokal yang Anda gunakan untuk mengakses server. Hal tersebut dapat di atasi dengan
melakukan konfigurasi pada sisi server.

>Catatan: Hak akses superuser diperlukan.

Untuk mengatasi time out koneksi SSH pada sisi server, cukup mengubah file `/etc/ssh/sshd_config`.

Pertama buka file tersebut dengan editor teks pilihan Anda :
```
$ sudo vim /etc/ssh/sshd_config
```
Lalu cari bari **ClientAliveInterval**, hilangkan tanda **#** dan ubah menjadi seperti ini :
```
ClientAliveInterval 120
```
Save hasil modifikasi dan restart service ssh:
```
$ sudo systemctl restart ssh
```
Atau
```
$ sudo systemctl restart sshd
```

***

Terima kasih sudah menyempatkan waktu untuk membaca tulisan ini.

Itulah cara mengatasi koneksi SSH terputus (time out) pada GNU/Linux. Jika dirasa ada yang kurang atau
Anda memiliki masukan, silahkan berikan komentar melalui kolom di bawah.

