# $Id$
# Maintainer: BlackEagle <ike.devolder@gmail.com>>

_gitname=kodi-addon-screensaver-matrixtrails
pkgname="$_gitname-git"
_commit=3323406
pkgver=20170610.3323406
pkgrel=1
pkgdesc="Matrix trails screensaver for Kodi"
arch=('i686' 'x86_64')
url='github.com/notspiff/screensaver.matrixtrails'
license=('GPL')
groups=('kodi-git-addons' 'kodi-git-addons-screensaver')
depends=('kodi-git' 'soil')
makedepends=('git' 'cmake' 'kodi-dev-git')
source=("$_gitname::git://github.com/notspiff/screensaver.matrixtrails.git#commit=$_commit")
sha256sums=('SKIP')

pkgver() {
	cd "$_gitname"
	git log -1 --date=short --format="%cd.%h" | tr -d '-'
}

build() {
	cd "$_gitname"
	cmake \
		-DCMAKE_INSTALL_PREFIX=/usr \
		-DCMAKE_BUILD_TYPE=Release \
		-DBUILD_SHARED_LIBS=1 \
		-DUSE_LTO=1
	make
}

package() {
	cd "$_gitname"
	make DESTDIR="$pkgdir/" install
}

