# Maintainer:  Markus Hansmair <archlinux at zendro dot de>

pkgname=mkinitcpio-systemd-extras
pkgver=0.5.4pre
pkgrel=3
pkgdesc="Manual testing of package mkinitcpio-systemd-extras"
arch=('any')
url="https://github.com/wolegis/mkinitcpio-systemd-extras"
license=('GPL')
depends=('mkinitcpio')
makedepends=('git')
optdepends=('tinyssh: for sd-tinyssh'
            'python: for converting OpenSSH host keys to tinyssh format'
            'dropbear: for sd-dropbear')
conflicts=('mkinitcpio-netconf' 'mkinitcpio-tinyssh' 'mkinitcpio-dropbear')
source=("sd-network"
        "sd-resolve"
        "sd-tinyssh"
        "sd-dropbear"
        "sd-hold")
sha256sums=('SKIP'
            'SKIP'
            'SKIP'
            'SKIP'
            'SKIP')

package() {
    local hookdir="${pkgdir}/usr/lib/initcpio/install"
    mkdir -p "${hookdir}"
    cp "${srcdir}/sd-"* "${hookdir}"
}
