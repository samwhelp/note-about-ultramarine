---
title: Boot ISO By GRUB
nav_order: 1040
has_children: false
parent: Boot ISO
grand_parent: ISO
---


# Boot ISO By GRUB




## 範例專案

* boot-iso-by-grub / [demo-boot-ultramarine-40-iso](https://github.com/samwhelp/ultramarine-adjustment/tree/main/core/iso/boot-iso/boot-iso-by-grub/demo-boot-ultramarine-40-iso)




## 下載 ISO

先參考「[Download ISO](https://samwhelp.github.io/note-about-ultramarine/read/core/iso/download-iso.html)」這篇提到的下載方式，下載「Ultramarine Linux 官方提供最新的ISO檔案」。

舉例：將「ISO檔案」放到「/opt/iso/ultramarine/40/ultramarine-xfce-40-live-x86_64.iso」這個路徑。

執行下面指令

``` sh
sudo curl -fLo /opt/iso/ultramarine/40/ultramarine-xfce-40-live-x86_64.iso --create-dirs \
	https://images.fyralabs.com/isos/ultramarine/40/ultramarine-xfce-40-live-x86_64.iso
```


## 設定範例

> 接著採用下面其中一種方式來設定。

| GRUB Boot ISO 範例 | 設定檔路徑 | 是否需要執行 update-grub |
| --- | --- | --- |
| demo_40_custom | [/etc/grub.d/40_custom](https://github.com/samwhelp/ultramarine-adjustment/blob/main/core/iso/boot-iso/boot-iso-by-grub/demo-boot-ultramarine-40-iso/asset/overlay/etc/grub.d/40_custom) | 修改後，需要執行 `sudo grub2-mkconfig -o /boot/grub2/grub.cfg` |
| demo_41_custom | [/boot/grub2/custom.cfg](https://github.com/samwhelp/ultramarine-adjustment/blob/main/core/iso/boot-iso/boot-iso-by-grub/demo-boot-ultramarine-40-iso/asset/overlay/boot/grub2/custom.cfg) | 修改後，**不需要**執行 `sudo grub2-mkconfig -o /boot/grub2/grub.cfg` |




## GRUB Menu Entry / Boot ISO 樣板 / ultramarine

``` sh

menuentry "Ultramarine 40 ISO / Flagship" --class Fedora {
	set iso_file="/opt/iso/ultramarine/latest/ultramarine-flagship-40-live-x86_64.iso"
	search --set=iso_partition --no-floppy --file $iso_file
	probe --set=iso_partition_uuid --fs-uuid $iso_partition
	set img_dev="/dev/disk/by-uuid/$iso_partition_uuid"
	loopback loop ($iso_partition)$iso_file
	#set boot_option=""
	#set boot_option="quiet splash"
	set boot_option="root=live:CDLABEL=UM-Flagship-Live rd.live.image enforcing=0 rhgb"
	linux (loop)/boot/vmlinuz-6.8.10-300.fc40.x86_64 iso-scan/filename=$iso_file $boot_option
	initrd (loop)/boot/initramfs-6.8.10-300.fc40.x86_64.img
}

```




## See Also

* Grub 探索筆記 / [GRUB Boot ISO 範例](https://samwhelp.github.io/note-about-grub/read/howto/boot_iso.html)
