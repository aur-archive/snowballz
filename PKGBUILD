# Maintainer: jsteel <mail at jsteel dot org>
# Contributor: Anton Bazhenov <anton.bazhenov at gmail>
# Contributor: Paolo Giangrandi <peoro.noob@gmail.com>
# Contributor: Marc poiroud <marciun@free.fr>

pkgname=snowballz
pkgver=0.9.5.1
pkgrel=5
pkgdesc="A fun RTS game featuring snowball fights with penguins"
arch=('any')
url="http://www.happypenguin.org/show?Snowballz"
license=('GPL')
depends=('python-opengl' 'python-pygame' 'python-rabbyt-old')
source=(http://ftp.debian.org/debian/pool/main/s/$pkgname/${pkgname}_$pkgver.orig.tar.gz
        $pkgname.patch
        $pkgname.png
        $pkgname.desktop
        $pkgname.sh)
md5sums=('197e3281cc85f9fe89a45c622e08ba0d'
         '11ed78c154b11fa0c776c46a162ea927'
         '70fcff90ac9fc65c4801236730473f46'
         '058e3dc39fb326f6ce260aa32082642c'
         'a52b50979645d74b200e9ff4d45cbb30')

build() {
  cd "$srcdir"/$pkgname-$pkgver

  patch -Np1 -i "$srcdir"/$pkgname.patch
}

package() {
  cd "$srcdir"/$pkgname-$pkgver

  install -dm755 "$pkgdir"/usr/share/$pkgname
  cp -r buildings cellulose gooeypy data maps plugins *.py "$pkgdir"/usr/share/$pkgname

  install -Dm755 "$srcdir"/$pkgname.sh "$pkgdir"/usr/bin/$pkgname
  install -Dm644 "$srcdir"/$pkgname.png "$pkgdir"/usr/share/pixmaps/$pkgname.png
  install -Dm644 "$srcdir"/$pkgname.desktop "$pkgdir"/usr/share/applications/$pkgname.desktop
  install -Dm644 README.txt "$pkgdir"/usr/share/doc/$pkgname/README
  install -m644 AUTHORS "$pkgdir"/usr/share/doc/$pkgname/AUTHORS
}
