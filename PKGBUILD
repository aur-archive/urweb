# Maintainer: Ben Darwin <bcdarwin@gmail.com>
# Maintainer: Michael Fellinger <mf@rubyists.com>
pkgname=urweb
pkgver=20140807
pkgrel=1
pkgdesc="A strict, pure functional language and libraries to support construction of dynamic web applications backed by SQL databases."
arch=('x86_64' 'i686')
url="http://www.impredicative.com/ur"
license=('GPL')
makedepends=('mlton')
depends=('gmp' 'openssl')
optdepends=('postgresql: for persistence'
            'sqlite: for persistence'
            'mariadb: for persistence'
            'htmlize-git: for syntax highlighting during demo generation'
            'smlnj: for interactively loading Ur/Web compiler modules')
source=(http://www.impredicative.com/ur/$pkgname-$pkgver.tgz)
sha256sums=('b9af0a35574c70ca24a1214fd99915117f42e5da07c9b8ecf194ead6405ebb1a')

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
