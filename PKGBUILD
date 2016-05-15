pkgname=sayonara-player
pkgver=20160514
_pkgver=0.9.0-git0
pkgrel=1
pkgdesc="Is a small, clear and fast audio player for Linux written in C++, supported by the Qt framework."
arch=( 'x86_64')
url="http://sayonara-player.com"
license=('GPL3')
depends=('qt5-base' 'taglib' 'gst-plugins-base' 'libmtp')
optdepends=('lame' 'gst-plugins-ugly')
makedepends=('cmake' 'qt5-tools')
source=("https://sayonara-player.com/sw/sayonara-player-${_pkgver}-${pkgver}.tar.gz")
md5sums=('9872c37ae48e8742bb471942d24ddfc1')


build() {
    cd $srcdir/$pkgname
    mkdir -p build && cd build
    cmake .. -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE="Release"
    make
}

package() {
        cd $srcdir/$pkgname/build
        make DESTDIR="$pkgdir/" install
}
