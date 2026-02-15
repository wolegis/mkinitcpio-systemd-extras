[Hans Månsson](https://github.com/hansmansson) fixed a [typo](https://github.com/wolegis/mkinitcpio-systemd-extras/pull/1) in `sd-resolve`.

[Spanfile](https://github.com/Spanfile) came up with a great suggestion to bring [predictable network interface names](https://github.com/wolegis/mkinitcpio-systemd-extras/pull/4) to the initramfs phase. I wish I had known about this option before publishing `sd-network`.

Later *Spanfile* extended the `sd-clevis` hook by adding the `clevis-decrypt-sss` binary. Now you can combine TPM2 and / or one or more tang servers in a highly customizable way.

[netzego](https://github.com/netzego) made me aware of the fact that [`sd-tinyssh` was implicitly dependent on the `base` install hook](https://github.com/wolegis/mkinitcpio-systemd-extras/pull/5).

[Amin Vakil](https://github.com/aminvakil) found a stupid [bug](https://github.com/wolegis/mkinitcpio-systemd-extras/issues/6) in v0.5.2 of `sd-network`. I had unnecessarily introduced a dependency on `cpio`.

[Markus Weinhold](https://github.com/marcusweinhold) contributed the pretty cool `sd-clevis` hook.

[Dwayne Bent](https://github.com/dbent) contributed the `sd-nftables` hook. Great stuff.

[reinerwein](https://github.com/rainerwein) discovered that `sd-clevis` failed when trying to contact a tang server over HTTPS due to [missing CA certificates](https://github.com/wolegis/mkinitcpio-systemd-extras/pull/13).
