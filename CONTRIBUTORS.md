2023-05-07 [Hans Månsson](https://github.com/hansmansson) fixed a [typo](https://github.com/wolegis/mkinitcpio-systemd-extras/pull/1) in `sd-resolve`.

2023-07-02 [Zeitwaechter](https://github.com/Zeitwaechter) suggested to make the [SSH port configurable](https://github.com/wolegis/mkinitcpio-systemd-extras/issues/2).

2023-12-20 [Spanfile](https://github.com/Spanfile) came up with a great suggestion to bring [predictable network interface names](https://github.com/wolegis/mkinitcpio-systemd-extras/pull/4) to the initramfs phase. I wish I had known about this option before publishing `sd-network`.

2024-01-27 [netzego](https://github.com/netzego) made me aware of the fact that [`sd-tinyssh` was implicitly dependent on the `base` install hook](https://github.com/wolegis/mkinitcpio-systemd-extras/pull/5). This is not the case anymore as `sd-tinyssh` and `sd-dropbear` now copy busybox to the initramfs image on their own if required.

2024-02-04 [Amin Vakil](https://github.com/aminvakil) found a stupid [bug](https://github.com/wolegis/mkinitcpio-systemd-extras/issues/6) in v0.5.2 of `sd-network`. I had unnecessarily introduced a dependency on `cpio`.

2024-07-18 [Markus Weinhold](https://github.com/marcusweinhold) contributed the pretty cool `sd-clevis` hook.

2024-09-18 [Dwayne Bent](https://github.com/dbent) contributed the `sd-nftables` hook. Great stuff.

2025-01-08 [reinerwein](https://github.com/rainerwein) discovered that `sd-clevis` failed when trying to contact a tang server over HTTPS due to [missing CA certificates](https://github.com/wolegis/mkinitcpio-systemd-extras/pull/13).

2025-05-28 [Spanfile](https://github.com/Spanfile) extended the `sd-clevis` hook by adding the [`clevis-decrypt-sss`](https://github.com/wolegis/mkinitcpio-systemd-extras/pull/14) binary. Now you can combine TPM2 and / or one or more tang servers in a highly customizable way.

2025-07-25 [Pedro Ferreira](https://github.com/pferreir) added a little [improvement](https://github.com/wolegis/mkinitcpio-systemd-extras/issues/15) to the documentation of `sd-network`.

2025-08-27 [Elouan Martinet](https://github.com/Exagone313) suggested mentioning [`rootflags=x-systemd.device-timeout=0`](https://github.com/wolegis/mkinitcpio-systemd-extras/issues/17) in the documentation. He was absolutely right, as omitting this kernel parameter can result in headless systems stuck in some emergency mode.

2025-11-14 [catch-404](https://github.com/catch-404) raised a minor [issue](https://github.com/wolegis/mkinitcpio-systemd-extras/issues/19) with `sd-dropbear` in conjunction with `systemd-tty-ask-password`. We found a solution and I adapted the documentation.

2025-12-02 [Sébastien Luttringer](https://github.com/seblu) found a [permission issue](https://github.com/wolegis/mkinitcpio-systemd-extras/issues/20) in hooks `sd-network` and `sd-resolve`. 

2025-12-03 Sébastien also found out that `sd-network` was [not copying `networkd.conf`](https://github.com/wolegis/mkinitcpio-systemd-extras/issues/22) and drop-ins. Stupid me.

2026-01-19 [Benjamin Flesch](https://github.com/bf) raised a (well-founded) [security concern](https://github.com/wolegis/mkinitcpio-systemd-extras/issues/26) about secret host keys being copied to the unencrypted initramfs image. The best solution I could come up with at this time was to emit a warning when OpenSSH keys are copied to the initramfs and additionally extend the documentation in this regard. But later...

2026-02-13 [Matthias R. Wiora](https://github.com/mrwiora) contributed a [variant of `sd-tinyssh`](https://github.com/wolegis/mkinitcpio-systemd-extras/pull/27) using `systemd-creds`, thus avoiding cleartext host keys in the initramfs image altogether. I [integrated his ideas](https://github.com/wolegis/mkinitcpio-systemd-extras/commit/55e5451210d8336358a0aa0b326565d905a89bf8) into the existing hooks `sd-tinyssh` and `sd-dropbear`.
