# Maintainer: Knut Ahlers <knut at ahlers dot me>

pkgname=korvike
pkgver=0.13.0
pkgrel=1
pkgdesc="korvike takes a Go template and executes it"
arch=('i686' 'x86_64')
url="https://github.com/Luzifer/$pkgname"
license=('Apache')
depends=()
makedepends=('go')
source=("${pkgname}-${pkgver}.tar.gz::${url}/archive/v${pkgver}.tar.gz")
sha512sums=('dffcdf394f93e587c9784543468684825b08b66c13190e645de8c3d5b5f9e92daad88e67e7393a0b2b6e6879c648bba54b452429e010ce340aa31a2bf1e51f30')

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
