# Maintainer: Ben Mather <bwhmather@bwhmather.com>

pkgname=libixp-git
pkgver=r158.a164e03
pkgrel=1
pkgdesc="Portable, simple C-language 9P client and server libary."
arch=('i686' 'x86_64')
url="https://github.com/bwhmather/libixp"
license=('MIT')
depends=()
makedepends=('git' 'txt2tags')
provides=("libixp")
conflicts=("libixp" "libixp-hg")
source=("libixp::git+https://github.com/bwhmather/libixp.git")
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/libixp"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  cd "$srcdir/libixp"
  make PREFIX=/usr
}

package() {
  cd "$srcdir/libixp"
  make DESTDIR="$pkgdir/" PREFIX=/usr install
  install -Dm644 README.md $pkgdir/usr/share/doc/libixp/README.md
  install -Dm644 LICENSE $pkgdir/usr/share/licenses/libixp/LICENSE
}

