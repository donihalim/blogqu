---
draft: false
date: 2020-02-17T22:46:28Z
title: "Cara Menambahkan Internal Border Di Xfce Dan Gnome Terminal"
subtitle: "Buat terminal lebih nyaman dipandang dengan menambahkan internal border atau padding"
seotitle: "Cara Menambahkan Internal Border Di Xfce dan Gnome Terminal"
description : "Internal border atau padding merupakan jarak antara teks dengan batas terminal yang
mana ditambahkan untuk kepentingan estetika."
slug: ""
categories:
- linux
- aplikasi
resources:
- src: "cover.jpeg"
  name: "cover"
- src: "*.jpeg"
---


Sampurasun.

Internal border atau padding merukapan jarak antara teks dan batas terminal, hal ini membuat output
teks menjadi lebih ketengah sehingga tidak terlalu rapat dengan terminal. Sangat berguna ketika Anda
sedang membaca _log_ melalui terminal saat melakukan debugging.

Hal ini juga cukup populer di kalangan para pegiat [kostumisasi desktop
GNU/Linux](https://m.facebook.com/groups/303997109715275?id=303997109715275&ref=content_filter&_rdr).

***

Pertama buka terminal (xfce/gnome-terminal) dengan kombinasi keyboard **CTRL+ALT+T** atau melalui
   launcher.

{{< photo src="terminal1.png" alt="Default Terminal" >}}

Lalu edit atau buat(jika belum ada) file `~/.config/gtk-3.0/gtk.css` :
```
$ vim ~/.config/gtk-3.0/gtk.css
```
Kemudian tambahkan baris dibawah ini:
```
vte-terminal {
    padding: 10px;
}
```
{{< photo src="terminal2.png" alt="Editing gtk.css" >}}

Ubah jarak **10px** sesuai keinginan Anda (misal 8px). Setelah itu simpan hasil editing dan tutup terminalnya
terlebih dahulu, kemudian buka kembali.

{{< photo src="terminal3.png" alt="Terminal Dengan Internal Border" >}}

***

Sekian untuk tulisan kali ini, jika ada yang ingin ditanyakan atau disampaikan silahkan gunakan kolom
komentar di bawah.

Hatur nuhun.

