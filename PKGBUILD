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
  mkdir -p $pkgdir/usr/bin
  install -m755 -t $pkgdir/usr/bin genpuid
  install -m755 -t $pkgdir/usr/bin mipcore
  mkdir -p $pkgdir/usr/share/doc/$pkgname
  install -m644 -t $pkgdir/usr/share/doc/$pkgname readme.txt
  install -m644 -t $pkgdir/usr/share/doc/$pkgname changelog.txt
  mkdir -p $pkgdir/usr/share/$pkgname
  install -m644 -t $pkgdir/usr/share/$pkgname ../keys.txt
}

check() {
  cd "$srcdir/$pkgname-$pkgver"
  if [ $pkgver = `./genpuid -v` ]; then
    echo "Package and installed versions are the same ($pkgver).";
    return 0;
  else
    echo "Version mismatch! Report to package maintainer!";
    return 1;
  fi
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  make DESTDIR="$pkgdir/" install
}

# vim:set ts=2 sw=2 et:
