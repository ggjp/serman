# Maintainer: Jean-Philippe Gagné Guay <jeanphilippe150 at gmail dot com>

_gitname=serman
pkgname=serman-git
pkgver=1
pkgrel=1
pkgdesc="A simple service manager (including an rc script)"
url="https://github.com/ggjp/serman"
arch=('any')
license=('GPL3')
depends=('sh')
makedepends=('git')
optdepends=('sinit: as init'
            'ubase: for halt, killall5 and getty')
source=('git+https://github.com/ggjp/serman.git')
sha256sums=('SKIP')

pkgver() {
  cd "$srcdir/$_gitname"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
  cd "$srcdir/$_gitname"
  mkdir -p "$pkgdir/usr/bin"
  cp -R etc/ "$pkgdir"
  mkdir -p "$pkgdir/etc/init.d/running"
  cp bin/serman "$pkgdir/usr/bin/"
}
