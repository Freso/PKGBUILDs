# Maintainer: Frederik "Freso" S. Olesen <freso.dk@gmail.com>
pkgname=genpuid
pkgver=1.4
pkgrel=1
pkgdesc=""
arch=(any)
url="http://musicbrainz.org/doc/GenPUID"
license=('unknown')
depends=('libstdc++5')
source=(http://ftp.musicbrainz.org/pub/musicbrainz/$pkgname/${pkgname}_linux_$pkgver.tgz
        http://ftp.musicbrainz.org/pub/musicbrainz/$pkgname/keys.txt)
md5sums=('fa4a6ae23adaaefa02f07de6321913fe'
         'b4c70151b073b80157106c8fe84fdc80')

build() {
  cd "$srcdir/$pkgname-$pkgver"
  ./configure --prefix=/usr
  make
}

check() {
  cd "$srcdir/$pkgname-$pkgver"
  make -k check
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  make DESTDIR="$pkgdir/" install
}

# vim:set ts=2 sw=2 et:
