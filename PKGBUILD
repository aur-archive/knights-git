
# Maintainer: Antonis G. (greenmanalishi) <capoiosct gmail.com>

pkgname=knights-git
pkgver=20111001
pkgrel=1
pkgdesc="Chess board with XBoard protocol support."
arch=('i686' 'x86_64')
url="http://kde-apps.org/content/show.php/Knights?content=122046"
license=('GPL2')
depends=('libkdegames')
optdepends=('gnuchess: for playing against the computer.')
makedepends=('automoc4' 'cmake' 'docbook-xsl' 'git')
groups=('kde' 'kdebase')
replaces=('kchess' 'knights-kde4' 'knights')
conflicts=('knights-kde4' 'knights')
source=("git://anongit.kde.org/knights")
install=$pkgname.install
sha1sums=('SKIP')

pkgver() {
  cd knights
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../knights \
      -DCMAKE_BUILD_TYPE=Release \
      -DCMAKE_INSTALL_PREFIX=$(kde4-config --prefix)
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
