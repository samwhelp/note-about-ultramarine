---
title: Upgrade System
nav_order: 1000
has_children: false
parent: Howto
---



# Upgrade System




## Link

* Ultramarine Linux / [Blog](https://blog.fyralabs.com/) / [Ultramarine 43 is Cooking with Gas](https://blog.fyralabs.com/ultramarine-43-release/)
* [https://ultramarine-linux.org/migrate.sh](https://ultramarine-linux.org/migrate.sh) ([Source](https://github.com/Ultramarine-Linux/website/blob/main/public/migrate.sh))




## Using DNF System Upgrades

> Run these commands to update the current install, and upgrade to Ultramarine 43:

``` sh
sudo dnf upgrade
sudo dnf system-upgrade download --releasever=43
sudo dnf system-upgrade reboot
```


## Converting from Fedora


### From Fedora 42 to Ultramarine Linux 43

``` sh
bash <(curl -s https://ultramarine-linux.org/migrate.sh)
sudo dnf system-upgrade download --releasever=43
sudo dnf system-upgrade reboot
```


### From Fedora 43 to Ultramarine Linux 43

``` sh
bash <(curl -s https://ultramarine-linux.org/migrate.sh)
```
