# Maintainer: Jonathan Liu <net147@gmail.com>
pkgname=gradm
pkgver=2.2.2
_timestamp=201111011031
pkgrel=6
pkgdesc="Administrative interface for the grsecurity Role Based Access Control system"
arch=('i686' 'x86_64')
url="http://grsecurity.net/"
license=('GPL2')
depends=('pam')
source=("http://grsecurity.net/stable/${pkgname}-${pkgver}-${_timestamp}.tar.gz")

build() {
  cd "${srcdir}/${pkgname}2"
  sed -i -e "s/^CFLAGS :=/CFLAGS +=/" "Makefile"
  make
}

package() {
  cd "${srcdir}/${pkgname}2"
  make DESTDIR="${pkgdir}/" INSTALL=/bin/install install
  rm "${pkgdir}"/dev/grsec > /dev/null
  rmdir "${pkgdir}"/dev > /dev/null
}

# vim:set ts=2 sw=2 et:
md5sums=('a7a259a2ae5179eaf5d277f40d919ddc')
