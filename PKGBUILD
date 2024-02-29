# Maintainer: Knut Ahlers <knut at ahlers dot me>

pkgname=korvike
pkgver=1.0.0
pkgrel=1
pkgdesc="korvike takes a Go template and executes it"
arch=('i686' 'x86_64')
url="https://github.com/Luzifer/$pkgname"
license=('Apache')
depends=()
makedepends=('go')
source=("${pkgname}-${pkgver}.tar.gz::${url}/archive/v${pkgver}.tar.gz")
sha512sums=('e17dfe2b812bc1a7f61e6760ff0186c0e4bf1e1380f10882ddca9999e3795c0001efe2c95b32f304e11a0842aedef0c7fc7ea005bf1c2a18c6c1ce16bc274abd')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  go build -a -v \
    -ldflags="-X main.version=${pkgver}" \
    -mod=readonly \
    -o korvike
}

package() {
  install -Dm755 -t "${pkgdir}/usr/bin" "${srcdir}/${pkgname}-${pkgver}/korvike"
}
