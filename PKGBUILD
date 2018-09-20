# Maintainer: Fredy García <frealgagu at gmail dot com>

pkgname=hp-cp1025nw-cups
pkgver=20151105
pkgrel=1
pkgdesc="CUPS drivers for printer HP cp1025nw"
arch=("i686" "x86_64")
url="https://github.com/frealgagu/hp-cp1025nw-cups"
license=("GPL" "custom")
depends=("psutils" "cups" "foomatic-db-engine")
makedepends=("bc" "unzip" "wget")
conflicts=("foo2zjs")
options=("!emptydirs" "!ccache")
install="foo2zjs.install"
source=("foo2zjs.tar.gz")
sha256sums=("f0d561df24d58e885278a5b6703d9149967d2383bdb05508b5ceee85703ef433")

build() {
  cd "${srcdir}/foo2zjs"

  make all
}

package() {
  cd "${srcdir}/foo2zjs"

  ./getweb 1025

  install -d "${pkgdir}/usr/share/"{applications,pixmaps,cups/model}
  install -d "${pkgdir}/usr/share/foomatic/db/source/"{driver,opt,printer}

  make DESTDIR="${pkgdir}" install

  install -D -m644 COPYING "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
