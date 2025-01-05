---
title: 連結
nav_order: 9000
has_children: false
---


# 連結




## News

* [Ultramarine Linux 40 Rains Down](https://blog.fyralabs.com/ultramarine-40-release/)




## Ultramarine Linux

* [Ultramarine Linux](https://ultramarine-linux.org/)
* [Ultramarine Package Sources](https://github.com/Ultramarine-Linux/packages)
* [Wiki](https://wiki.ultramarine-linux.org/en/welcome/)
* [Download](https://ultramarine-linux.org/download/)
* [GitLab](https://gitlab.com/ultramarine-linux)
* [GitHub](https://github.com/Ultramarine-Linux)
* [migrate.sh](https://github.com/Ultramarine-Linux/website/blob/main/static/migrate.sh)

``` sh
bash <(curl -s https://ultramarine-linux.org/migrate.sh)
```




## Fyra Labs

* [Fyra Labs](https://fyralabs.com/)
* [GitHub](https://github.com/FyraLabs)



## Katsu

* [Katsu](https://developer.fyralabs.com/katsu)
* GitHub / FyraLabs / [katsu](https://github.com/FyraLabs/katsu)
* GitHub / Ultramarine-Linux /  [images](https://github.com/Ultramarine-Linux/images)
* [fedora-bootstap-notes](https://github.com/zpangwin/fedora-bootstap-notes/tree/main)


### fedora bootstrap

> fedora-bootstap-notes / scripts / 001 / [02-pre-chroot-setup.sh](https://github.com/zpangwin/fedora-bootstap-notes/blob/main/scripts/001/02-pre-chroot-setup.sh#L96-L97)

``` sh
# install minimal fedora setup
dnf --releasever=36 --installroot=/mnt -y groupinstall core;
```

> fedora-bootstap-notes / scripts / 002 / [02-pre-chroot-setup.sh](https://github.com/zpangwin/fedora-bootstap-notes/blob/main/scripts/002/02-pre-chroot-setup.sh#L113-L114)

``` sh
# install minimal fedora setup
dnf --releasever=36 --installroot=/mnt -y groupinstall core;
```


> katsu / src / [builder.rs](https://github.com/FyraLabs/katsu/blob/main/src/builder.rs#L361)

``` rust
		info!("Initializing system with dnf");
		crate::run_cmd_prep_chroot!(&chroot,
			$dnf install -y --releasever=$releasever --installroot=$chroot $[packages] $[options] 2>&1;
			$dnf clean all --installroot=$chroot;
		)?;
```



### xorriso

> katsu / src / [builder.rs](https://github.com/FyraLabs/katsu/blob/main/src/builder.rs#L807)

``` rust
debug!("xorriso -as mkisofs --efi-boot {uefi_bin} -b {bios_bin} -no-emul-boot -boot-load-size 4 -boot-info-table --efi-boot {uefi_bin} -efi-boot-part --efi-boot-image --protective-msdos-label {root} -volid KATSU-LIVEOS -o {image}", root = tree.display(), image = image.display());
```


### mksquashfs

> katsu / src / [builder.rs](https://github.com/FyraLabs/katsu/blob/main/src/builder.rs#L704)

``` rust
info!("Squashing file system (mksquashfs)");
std::process::Command::new("mksquashfs")
	.arg(chroot)
	.arg(image)
	.args(&sqfs_comp_args)
	.arg("-b")
	.arg("1048576")
	.arg("-noappend")
	.arg("-e")
	.arg("/dev/")
	.arg("-e")
	.arg("/proc/")
	.arg("-e")
	.arg("/sys/")
	.arg("-p")
	.arg("/dev 755 0 0")
	.arg("-p")
	.arg("/proc 755 0 0")
	.arg("-p")
	.arg("/sys 755 0 0")
	.args(&sqfs_extra_args)
	.status()?;

```


### qemu

> [qemu.sh](https://github.com/Ultramarine-Linux/images/blob/um41/qemu.sh)




## Just the Docs

* [Just the Docs](https://pmarsceill.github.io/just-the-docs/) ([GitHub](https://github.com/pmarsceill/just-the-docs))
* [Demo](https://pmarsceill.github.io/jtd-remote/) ([GitHub](https://github.com/pmarsceill/jtd-remote))
