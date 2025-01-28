# Maintainer: Knut Ahlers <knut at ahlers dot me>

pkgname=korvike
pkgver=1.0.4
pkgrel=1
pkgdesc="korvike takes a Go template and executes it"
arch=('i686' 'x86_64')
url="https://github.com/Luzifer/$pkgname"
license=('Apache')
depends=()
makedepends=('go')
source=("${pkgname}-${pkgver}.tar.gz::${url}/archive/v${pkgver}.tar.gz")
sha512sums=('d530ee8f6ea0830757f17f10e0651f35b37122009a7b24bb0681f2a3f7fe83e4433562e7d024fcfba3701fa3826178e0a78256373044537d44a4036ea2626751')

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
