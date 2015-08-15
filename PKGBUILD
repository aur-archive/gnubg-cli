# Maintainer: jsteel <mail at jsteel dot org>
# Contributor: Dmitrij D. Czarkoff <czarkoff@gmail.com>

pkgname=gnubg-cli
_pkgname=gnubg
pkgver=20121201
pkgrel=1
pkgdesc="A world class backgammon application (command line interface)"
arch=('i686' 'x86_64')
url="http://www.gnubg.org"
license=('GPL')
depends=('python2' 'glib2')
makedepends=('bison' 'flex')
conflicts=('gnubg' 'gnubg-cvs')
source=($url/media/sources/$_pkgname-source-SNAPSHOT-$pkgver.tar.gz)
md5sums=('6fb0d363169de1007d9af5e8e5e1690d')

build() {
  cd "$srcdir"/$_pkgname

  ./autogen.sh

  ./configure --prefix=/usr --bindir=/usr/bin --sysconfdir=/etc --mandir=/usr/share/man --without-gtk

  make
}

package() {
  cd "$srcdir"/$_pkgname

  make DESTDIR="$pkgdir" install

  rm -r "$pkgdir"/usr/share/icons
}
