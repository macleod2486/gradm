# Maintainer: Jonathan Liu <net147@gmail.com>
pkgname=gradm
pkgver=2.9.1
_timestamp=201207201554
pkgrel=1
pkgdesc="Administrative interface for the grsecurity Role Based Access Control system"
arch=('i686' 'x86_64')
url="http://grsecurity.net/"
license=('GPL2')
depends=('pam')
source=("http://grsecurity.net/stable/${pkgname}-${pkgver}-${_timestamp}.tar.gz")
sha256sums=('59f94b4f9bfde19b8deddc86a3c8d5bad77a77ae2f80c7952519447814e10db3')

build() {
  cd "${srcdir}/${pkgname}2"
  sed -i -e "s/^CFLAGS :=/CFLAGS +=/" "Makefile"
  make
}

package() {
  cd "${srcdir}/${pkgname}2"
  make DESTDIR="${pkgdir}" install
  rm "${pkgdir}"/dev/grsec > /dev/null
  rmdir "${pkgdir}"/dev > /dev/null
}

# vim:set ts=2 sw=2 et:
