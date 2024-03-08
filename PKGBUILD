# Maintainer: Knut Ahlers <knut at ahlers dot me>

pkgname=korvike
pkgver=1.0.1
pkgrel=1
pkgdesc="korvike takes a Go template and executes it"
arch=('i686' 'x86_64')
url="https://github.com/Luzifer/$pkgname"
license=('Apache')
depends=()
makedepends=('go')
source=("${pkgname}-${pkgver}.tar.gz::${url}/archive/v${pkgver}.tar.gz")
sha512sums=('f4f5f1a33cc68f9411ee3c03d803c5e748797167397f9373056e2cf74e191263cf81b321a26656518fd602d2dd19a79ce36c00c26ab2a285b63d63ff13edebb5')

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
