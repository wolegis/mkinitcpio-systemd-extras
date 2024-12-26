# mkinitcpio-systemd-extras

This is a collection of `mkinitcpio` install hooks for systemd based
initramfs.

[mkinitcpio](https://wiki.archlinux.org/title/Mkinitcpio) is an Arch Linux
specific tool to generate images for the [initial ramdisk
(initramfs)](https://wiki.archlinux.org/title/Arch_boot_process#initramfs)
required during early boot of an Arch Linux installation. There are two options
how this boot phase can be executed:

* A bunch of shell scripts run by the busybox shell.

* Systemd is started already in this initramfs environment and any
  initialization is performed by means of systemd units.

This repository provides so-called install hooks that can be used in
`mkinitcpio`'s configuration file `mkinitcpio.conf`. They complement the set of
install hooks for a systemd based boot process provided by other packages like
e.g. *systemd*, *mkinitcpio*, *cryptsetup*, *lvm2*, ...

> [!CAUTION]
> Tinkering with the boot process of your system is always risky.  Make sure
> that you always have at least one option to back out.

## Installation

*mkinitcpio-systemd-extras* is available as a
[package](https://aur.archlinux.org/packages/mkinitcpio-systemd-extras) in Arch
Linux' User Repository (AUR). Use `makepkg` to build and `pacman` to install
the package.  (Alternatively you may use your favorite [AUR
helper](https://wiki.archlinux.org/title/AUR_helpers).)

## Usage

See the short help available for each install hook, e.g.

```bash
mkinitcpio -H sd-tinyssh
```

For more details see the corresponding [wiki pages](../../wiki).

## Contribution

You are welcome to provide additional hooks or improvements of the existing
ones in the form of pull requests. Mind that all hooks must provide some degree
of general usefulness.
