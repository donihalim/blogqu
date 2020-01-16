---
draft: false
date: 2019-09-18T16:41:21+07:00
title: "24 Jam Pertama dengan PureOS"
subtitle: "Migrasi ke GNU/Linux"
seotitle: "24 Jam Pertama dengan GNU/Linux PureOS"
description : "Hubungan PureOS dengan Free Software Foundation (FSF) dan alasan masuk akal penulis mengapa memilih PureOS."
slug: "24-jam-pertama-dengan-pureos"
categories:
- desktop
resources:
- src: "cover.jpeg"
  name: "cover"
- src: "*.jpeg"
---

Bismillahirrohmanirrohim.

PureOS adalah Distribusi turunan Debian yang memiliki tampilan sederhana, moderen, eklusif dan bebas. PureOS hanya membawa aplikasi yang merdeka dan merupakan salah satu distribusi selain [Trisquel] dan [gNewSense] yang didukung oleh [Free Software Foundation].

Di situs resminya mengatakan PureOS adalah distribusi yang mengutamakan privasi pengguna dengan membawa sejumlah aplikasi desktop. Karena lingkungan desktop menggunakan GNOME saya rasa cocok untuk pemula, dalam artian seperti anak-anak, mahasiswa, jurnalis, orang tua, dan bahkan untuk tetangga Anda.

Beberapa orang migrasi dari distribusi satu ke lainnya masih dikatakan wajar, sebab GNU/linux memiliki ratusan varian distribusi, dengan berbagai lingkungan desktop, berbagai aplikasi standar dan faktor selera pengguna yang berbeda pula.

Namun ada beberapa alasan masuk akal migrasi atau pindah distribusi ke PureOS, Berikut daftar ulasan dan fiturnya.

***

## Live CD

PureOS memiliki kelebihan yaitu Live CD. Gunanya untuk mengecek hardware apa saja yang didukung. PureOS juga memiliki tampilan yang indah karena memakai tema gelap saat dijadikan Live CD, dan memiliki Hardware Detection Tool (HDT) serta Memory Diagnostic Tool di bagian Pilihan Lanjutan (Advanced Options).

{{< photoset max="2" >}}
  {{< photo src="1.jpeg" alt="live-cd-1" >}}
  {{< photo src="2.jpeg" alt="live-cd-2" >}}
{{</ photoset >}}

## Perbedaan

Apa saja perbedaan PureOS dengan distribusi lain? Tidak terlalu banyak, diantaranya:

- PureOS adalah salah satu GNU/Linux Sistem Operasi yang benar-benar 100% Free, artinya tidak ada aplikasi non-free baik propietary, dan/atau driver/firmware.
- PureOS sudah dikonfigurasi dengan privasi dan keamanan lapisan ganda. Seperti isolasi aplikasi dengan Wayland dan AppArmor aktif secara bawaan
- Terdapat PureBrowser penjelajah web yang dibuat dari teknologi Mozilla.
- Rolling-release model, Artinya jika ada pembaruan maka aplikasi dan driver segera diperbarui dengan fitur, keamanan, performa, atau perbaikan kutu.

Jadi dengan Rolling-release ini orang tidak perlu mengupgrade ke versi selanjutnya dengan menghabiskan kuota internet sekian giga, sebab PureOS akan memperbarui sistemnya setiap hari jika ada pembaruan.

Juga perlu diketahui secara bawaan pengaturan lokasi tidak aktif.

{{< photoset max="2" >}}
  {{< photo src="3.jpeg" alt="perbedaan-1" >}}
  {{< photo src="4.jpeg" alt="perbedaan-2" >}}
{{</ photoset >}}

## Endorse

PureOS salah satu sistem operasi yang diendorse langsung oleh [Free Software Foundation]. Selain PureOS [Free Distro] dari [FSF] diantaranya:

- [Dragora]
- [Dyne]
- [gNewSense]
- [Guix]
- [Hyperbola]
- [Trisquel]
- [Ututo]

## Tampilan dan Pengalaman pengguna (UI/UX)

Beberapa orang yang pernah memakai debian, ubuntu, atau fedora akan lebih mengerti tentang tampilan pengguna GNOME. Lingkungan desktop GNOME mempunyai tampilan yang bersih, solid, dan minimalis. Orang awam akan mudah paham jika diberikan lingkungan desktop seperti GNOME ini.

{{< photoset max="2" >}}
  {{< photo src="5.jpeg" alt="gnome-1" >}}
  {{< photo src="6.jpeg" alt="gnome-2" >}}
{{</ photoset >}}

Secara bawaan GNOME menggunakan Wayland sebagai sesi bawaan, jika mesin Anda tidak didukung bisa menggunakan Xorg seperti pada mesin laptop saya Dell Vostro 3350 yang masih menggunakan mesin lama dan belum mampu untuk memakai Wayland secara optimal. Oleh karena itu diharuskan mengganti pengaturan Wayland Gnome Display Manager (GDM) ke X agar touchpad tidak muncul ganda.

```
sudo -H gedit /etc/gdm3/daemon.conf
```

dan hilangkan tanda pagar # menjadi
```
WaylandEnable=false
```

Tentu cara ini tergantung mesin anda apakah didukung Wayland apa tidak, karena mesin penulis lumayan jadul saya pakai cara ini agar GNOME memakai X saja.

## Mendukung Pen Tablet

Alhamdulillah, Pen tablet wacom bisa terdeteksi dengan mudah tanpa driver. Pen Tablet juga sebagai pengganti tetikus sekaligus alat yang dibutuhkan ilustrator. Bagi penulis, Pen tablet mengurangi kemalasan dan meningkatkan produktifitas.

{{< photoset max="2" >}}
  {{< photo src="7.jpeg" alt="pen-tablet-gnome-1" >}}
  {{< photo src="8.jpeg" alt="pen-tablet-gnome-2" >}}
{{</ photoset >}}


## Bermain dan memutarkan apapun
Hal yang mengejutkan bagi penulis yang dikutip dari FAQ PureOS.

*"Will I be able to open photos, videos and music from my Windows/MacOS computers?"*

*Yes. PureOS supports many multimedia file formats.*

Meskipun hanya dengan Free Software, orang bisa memainkan berbagai berkas musik dan video seperti mp3, mp4, mkv dan ekstensi media lainnya.

{{< photoset max="2" >}}
  {{< photo src="9.jpeg" alt="memutarkan-musik" >}}
  {{< photo src="10.jpeg" alt="memutarkan-video" >}}
{{</ photoset >}}

## Kostumisasi

PureOS memberikan aplikasi GNOME Tweak Tool secara bawaan, tentunya orang akan diberikan kebebasan untuk memodifikasi tampilan GNOME Shell. Seperti merubah ikon, fonta, shell tema, kursor dan gambar latar belakang.

{{< photoset max="2" >}}
  {{< photo src="11.jpeg" alt="gnome-tweak-1" >}}
  {{< photo src="12.jpeg" alt="gnome-tweak-2" >}}
{{</ photoset >}}

## Aplikasi bawaan

PureOs sudah berisi aplikasi yang siap untuk digunakan sehari-hari seperti dibawah ini.

- Aplikasi Perkantoran : [LibreOffice]
- Penjelajah Web : PureBrowser (Hasil dari teknologi Mozilla)
- Email klien : ThunderBird
- Pembuka Musik : Rhythmbox
- Pembuka Video : Totem
- Virtualisasi : Gnome Boxes 

{{< photoset max="2" >}}
  {{< photo src="13.jpeg" alt="libreroffice" >}}
  {{< photo src="14.jpeg" alt="purebrowser" >}}
{{</ photoset >}}

{{< photoset max="3" >}}
  {{< photo src="15.jpeg" alt="default-application-pureos" >}}
  {{< photo src="16.jpeg" alt="gnome-boxes" >}}
  {{< photo src="17.jpeg" alt="rhythmbox dan totem" >}}
{{</ photoset >}}

## Kemudahan

Dalam segi kemudahan PureOS merupakan Sistem Operasi yang sangat mudah di atur setelah baru pasang OS. Orang cukup memperbarui di Software Center dan mengeklik ikon Update. Tidak perlu menginstall codec untuk memainkan musik dan video sebab sudah tersedia codec. Tidak perlu memasang aplikasi perkantoran penjelajah web dan email klien. Tidak perlu dipasang karena sudah ada. Di bagian ini Saya hanya memasang Inkscape dan Gimp untuk kebutuhan mendesain dan ilustrasi.

{{< photoset max="2" >}}
  {{< photo src="18.jpeg" alt="software-updater-1" >}}
  {{< photo src="19.jpeg" alt="software-updater-2" >}}
{{</ photoset >}}

## Pusat Aplikasi

PureOS adalah turunan dari Debian yang menggunakan GNOME. Artinya orang dapat menggunakan Software Center untuk menginstall, menghapus, dan memperbarui aplikasi dengan mudah.

{{< photoset max="2" >}}
  {{< photo src="20.jpeg" alt="gnome-software" >}}
  {{< photo src="21.jpeg" alt="gnome-software" >}}
{{</ photoset >}}

## Pengguna yang beruntung

Jika orang sudah mencoba live CD dan memasang di media penyimpanan hardisk. Saya katakan orang tersebut adalah orang yang beruntung, sebab jelas sudah mesin-mesin yang dipakainya tersebut didukung oleh GNU/Linux. Karena jarang mesin-mesin di Indonesia yang free meskipun tidak semuanya non-free/propietary. Terkadang orang harus memasang aplikasi/driver/firmware propietary agar mesin berjalan dengan optimal. Saya katakan lagi "Hebat, orang memakai GNU/Linux yang benar-benar 100% *Free* dan menghargai privasi dengan PureOS".

## Pranala Penting

Berikut ini beberapa pranala penting tentang PureOS.

- [Laman Unduh PureOS](https://www.pureos.net/download/)
- [Kode sumber](http://repo.pureos.net/pureos/pool/main/)
- [Mengecek kompatibilitas mesin anda](https://tracker.pureos.net/w/pureos/hardware_requirements/)
- [Kumpulan aplikasi PureOS](http://software.pureos.net/)
- [Seputar Pertanyaan dan jawaban](https://tracker.pureos.net/w/faq/)

Sekian, semoga bermanfaat.

***

[Free Software Foundation]:https://www.fsf.org/
[FSF]:https://www.fsf.org/
[Free Distro]:https://www.gnu.org/distros/free-distros.en.html
[LibreOffice]:https://www.libreoffice.org/
[Dragora]:https://dragora.org/en/index.html
[Dyne]:https://www.dyne.org/software/dynebolic
[gNewSense]:https://gnewsense.org/
[Guix]:https://www.gnu.org/software/guix/
[Hyperbola]:https://www.hyperbola.info/?gnu-free-stros-page
[Trisquel]:https://trisquel.info
[Ututo]:https://www.ututo.net
