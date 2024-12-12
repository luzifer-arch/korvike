# Maintainer: Knut Ahlers <knut at ahlers dot me>

pkgname=korvike
pkgver=1.0.3
pkgrel=1
pkgdesc="korvike takes a Go template and executes it"
arch=('i686' 'x86_64')
url="https://github.com/Luzifer/$pkgname"
license=('Apache')
depends=()
makedepends=('go')
source=("${pkgname}-${pkgver}.tar.gz::${url}/archive/v${pkgver}.tar.gz")
sha512sums=('459358c8c6c593caa2bd1ec08952cd9780bbbf245971f83de907c4d488fefc4e5640f1ada0bfc82967bf4de4692468ba46f8af3b855da208a4e229d2ee9ae259')

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
