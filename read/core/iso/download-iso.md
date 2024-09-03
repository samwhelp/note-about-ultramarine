---
title: Download ISO
nav_order: 1000
has_children: false
parent: ISO
---


# Download ISO

* [下載腳本](#下載腳本)
* [下載點](#下載點)
* [下載方式](#下載方式)




## 下載腳本

* [下載腳本](https://github.com/samwhelp/ultramarine-adjustment/tree/main/core/iso/boot-iso/boot-iso-by-grub/demo-boot-ultramarine-40-iso)




## 下載點

> 可以到「Ultramarine Linux / [Download](https://ultramarine-linux.org/download/)」，找到相關的下載點。

> 也可以在「[https://images.fyralabs.com/isos/ultramarine/40/](https://images.fyralabs.com/isos/ultramarine/40/)」，找到相關的下載點。




## 下載方式


### iso-download.txt

先產生一個檔案「iso-download.txt」，內容如下

```
https://images.fyralabs.com/isos/ultramarine/40/ultramarine-flagship-40-live-x86_64.iso
https://images.fyralabs.com/isos/ultramarine/40/ultramarine-gnome-40-live-x86_64.iso
https://images.fyralabs.com/isos/ultramarine/40/ultramarine-xfce-40-live-x86_64.iso
https://images.fyralabs.com/isos/ultramarine/40/ultramarine-kde-40-live-x86_64.iso




https://images.fyralabs.com/isos/ultramarine/40/ultramarine-flagship-40-live-x86_64.iso.sha256sum
https://images.fyralabs.com/isos/ultramarine/40/ultramarine-gnome-40-live-x86_64.iso.sha256sum
https://images.fyralabs.com/isos/ultramarine/40/ultramarine-xfce-40-live-x86_64.iso.sha256sum
https://images.fyralabs.com/isos/ultramarine/40/ultramarine-kde-40-live-x86_64.iso.sha256sum
```


### iso-download.sh

接著執行下面的指令，就會下載剛剛「iso-download.txt」裡面所列的檔案

``` sh
wget -c -i iso-download.txt
```

> 關於「-c」指的是續傳

> 關於「-i iso-download.txt」，指的是下載「iso-download.txt」裡面所列的檔案




## Boot ISO

> 簡單「[驗證](#驗證)」過「下載完成的ISO檔案」，接下來可以選擇不同的「[Boot ISO](https://samwhelp.github.io/note-about-ultramarine/read/core/iso/boot-iso.html)」方式。




## 驗證




## 列表

| Spins | ISO | Checksum |
| ----- | --- | -------- |
| Budgie (Flagship) | [ultramarine-flagship-40-live-x86_64.iso](https://images.fyralabs.com/isos/ultramarine/40/ultramarine-flagship-40-live-x86_64.iso) | [ultramarine-flagship-40-live-x86_64.iso.sha256sum](https://images.fyralabs.com/isos/ultramarine/40/ultramarine-flagship-40-live-x86_64.iso.sha256sum) |
| Gnome Shell | [ultramarine-gnome-40-live-x86_64.iso](https://images.fyralabs.com/isos/ultramarine/40/ultramarine-gnome-40-live-x86_64.iso) | [ultramarine-gnome-40-live-x86_64.iso.sha256sum](https://images.fyralabs.com/isos/ultramarine/40/ultramarine-gnome-40-live-x86_64.iso.sha256sum) |
| Xfce | [ultramarine-xfce-40-live-x86_64.iso](https://images.fyralabs.com/isos/ultramarine/40/ultramarine-xfce-40-live-x86_64.iso) | [ultramarine-xfce-40-live-x86_64.iso.sha256sum](https://images.fyralabs.com/isos/ultramarine/40/ultramarine-xfce-40-live-x86_64.iso.sha256sum) |
| Kde Plasma | [ultramarine-kde-40-live-x86_64.is](https://images.fyralabs.com/isos/ultramarine/40/ultramarine-kde-40-live-x86_64.iso) | [ultramarine-kde-40-live-x86_64.iso.sha256sum](https://images.fyralabs.com/isos/ultramarine/40/ultramarine-kde-40-live-x86_64.iso.sha256sum) |
