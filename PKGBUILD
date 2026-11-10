# Maintainer: DasSkelett <dasskelett@dasskelett.dev>
pkgname=yanic
pkgver=2.1.1+batmanv4
pkgrel=2
pkgdesc='A respondd client that fetches, stores and publishes information about a Freifunk network'
arch=('amd64' 'arm64')
makedepends=('golang')
backup=('/etc/yanic.conf')
license=('AGPL-3.0')
url='https://github.com/freifunkMUC/yanic'

source=("${pkgname}-${pkgver}::https://github.com/freifunkMUC/yanic/archive/refs/tags/v${pkgver}.tar.gz")
sha256sums=('251286ad255ab06a00788a3a104c426ef2c383060422665acc3333c8b74dcad0')

build() {
    cd "${pkgname}-${pkgver//+/-}/"
    go build -trimpath -buildvcs=false -o "${pkgname}"
}

package() {
    cd "${pkgname}-${pkgver//+/-}/"
    install -Dm755 "${pkgname}" "${pkgdir}/usr/local/bin/${pkgname}"
    install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
    install -Dm644 config_example.toml "${pkgdir}/etc/${pkgname}.conf"

    # install -Dm644 "contrib/init/linux-systemd/${pkgname}.service" "${pkgdir}/etc/systemd/system/${pkgname}.service"
}

# https://docs.makedeb.org/makedeb/pkgbuild-syntax/
# vim: set sw=4 expandtab:
