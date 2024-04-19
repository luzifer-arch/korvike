# Maintainer: Knut Ahlers <knut at ahlers dot me>

pkgname=korvike
pkgver=1.0.2
pkgrel=1
pkgdesc="korvike takes a Go template and executes it"
arch=('i686' 'x86_64')
url="https://github.com/Luzifer/$pkgname"
license=('Apache')
depends=()
makedepends=('go')
source=("${pkgname}-${pkgver}.tar.gz::${url}/archive/v${pkgver}.tar.gz")
sha512sums=('9b0bd431a2a2d73960b2090117db9aa817d66aea3b442b25cc8b8050033f96f4830da0b2e11b5d5c0eaad073d38aff2ce2842ebed10785ccf6a0ab45584c7d74')

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
