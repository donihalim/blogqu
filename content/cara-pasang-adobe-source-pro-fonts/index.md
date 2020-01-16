---
draft: false
date: 2019-09-12T08:47:06+07:00
title: "Cara Pasang Adobe Source Pro Fonts"
subtitle: ""
seotitle: "Cara Pasang Adobe Source Pro Fonts- Hervy Qurrotul Ainur Rozi"
description : "Adobe Source Pro Fonts"
type: "fonta"
resources:
- src: "*.jpeg"
- src: "1.jpeg"
  name: "cover"
---

{{< photo src="cover.jpeg" alt="Cara Pasang Adobe Source Sans Pro" >}}

### **openSUSE**
```
sudo zypper install adobe-source-sans-pro-fonts adobe-source-serif-pro-fonts adobe-source-code-pro-fonts
```

### **Fedora/Centos/RedHat**
```
sudo dnf install adobe-source-sans-pro-fonts adobe-source-serif-pro-fonts adobe-source-code-pro-fonts
```

### **Arch/Manjaro**
```
sudo pacman -S adobe-source-sans-pro-fonts adobe-source-serif-pro-fonts adobe-source-code-pro-fonts
```

### **Debian/Ubuntu/Mint/Neon**

```
mkdir /tmp/adodefont
cd /tmp/adodefont
mkdir -pv ~/.fonts
wget https://gitlab.com/hervyqa/adobe-source-pro-fonts/uploads/20837d66cdb3323369517783c2e6ee54/adobe-source-pro-fonts-otf.zip
unzip -x adobe-source-pro-fonts-otf.zip
mv adobe-source-pro-fonts-otf ~/.fonts
fc-cache -f -v
```

### **Windows**

* Klik **[DOWNLOAD](https://gitlab.com/hervyqa/adobe-source-pro-fonts/uploads/20837d66cdb3323369517783c2e6ee54/adobe-source-pro-fonts-otf.zip)**
* Kemudian ekstrak zip.
* Buka direktori adobe-source-pro-fonts-otf
* Kemudian, pilih semua fonta.
* Klik kanan, Pilih "Install Font".
