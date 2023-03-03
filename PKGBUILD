# Maintainer:  Markus Hansmair <archlinux at zendro dot de>

pkgname=mkinitcpio-systemd-extras
pkgver=0.3pre
pkgrel=1
pkgdesc="Manual testing of package mkinitcpio-systemd-extras"
arch=('any')
url="https://github.com/wolegis/mkinitcpio-systemd-extras"
license=('GPL')
depends=('mkinitcpio')
optdepends=('tinyssh: for sd-tinyssh'
            'python: for converting OpenSSH host keys to tinyssh format')
conflicts=('mkinitcpio-netconf' 'mkinitcpio-tinyssh')
source=("sd-network"
        "sd-resolve"
        "sd-tinyssh"
        "sd-hold")
sha256sums=('SKIP'
            'SKIP'
            'SKIP'
            'SKIP')

package() {
    local hookdir="${pkgdir}/usr/lib/initcpio/install"
    mkdir -p "${hookdir}"
    cp "${srcdir}/sd-"* "${hookdir}"
}
