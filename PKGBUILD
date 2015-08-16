# Contributor: Piotr Gorski <prgorski88@gmail.com>

pkgname=kadu-0.11.3
pkgver=0.11.3
_pkgver=0.11.3
pkgrel=10
pkgdesc="A Qt-based Gadu-Gadu/Jabber client"
arch=('i686' 'x86_64')
url="http://www.kadu.im/"
license=('GPL')
depends=('qt4' 'libgadu' 'libidn' 'libmpdclient' 'qtwebkit' 'phonon' 'qca' 'qca-ossl')
makedepends=('cmake' 'aspell' 'libao' 'libsndfile' 'libxtst' 'curl' 'libxss')
conflicts=('kadu-svn' 'kadu' 'kadu-beta1' 'kadu-beta2')
source=(http://download.kadu.im/stable/kadu-$_pkgver.tar.bz2)
md5sums=('fc70882b86bdb04cb0835b2cf014b8aa')

build() {
  cd $srcdir/kadu-$_pkgver

  cmake . -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE="Release"
  make || return 1
  make DESTDIR=$pkgdir install || return 1

  rm -rf $pkgdir/usr/{lib,include}/{libgadu*,pkgconfig}
  rm -rf $pkgdir/usr/share/kadu/{HISTORY,README}
}
