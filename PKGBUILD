# Maintainer: Alexander Minges <alexander.minges@gmail.com>
pkgname=xds-viewer
pkgver=0.6
pkgrel=3
pkgdesc="XDS-Viewer is a program for viewing X-ray diffraction and control images."
url="http://xds-viewer.sourceforge.net/"
arch=('x86_64' 'i686')
license=('GPLv2')
depends=('qt4')
makedepends=('cmake')
optdepends=('xds-bin: for external conversion utilities')
source=("http://sourceforge.net/projects/${pkgname}/files/${pkgname}/${pkgname}-${pkgver}/${pkgname}-${pkgver}.tar.gz")
md5sums=('e2a61c9a22b187594f7f2d9271542c98')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  cmake ./ -DCMAKE_INSTALL_PREFIX=/usr
  make
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  make DESTDIR="${pkgdir}" install
  install -Dm644 COPYING "$pkgdir/usr/share/licenses/$pkgname/COPYING"
}
