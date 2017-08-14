pkgname=sayonara-player
pkgver=20170509
_pkgver=0.9.3-git2
pkgrel=1
pkgdesc="Sayonara is a small, clear and fast audio player for Linux written in C++, supported by the Qt framework. It uses Gstreamer as audio backend."
arch=( 'x86_64')
url="http://sayonara-player.com"
license=('GPL3')
depends=('qt5-base' 'taglib' 'gst-plugins-base' 'libmtp')
optdepends=('lame' 'gst-plugins-ugly')
makedepends=('cmake' 'qt5-tools')
source=("https://sayonara-player.com/sw/sayonara-player-${_pkgver}-${pkgver}.tar.gz")
md5sums=('9581bb4157a687b561558baf60aa83b6')

build() {
    cd $pkgname
    mkdir -p build && cd build
    cmake .. -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE="Release"
    make
}

package() {
        cd $pkgname/build
        make DESTDIR="$pkgdir/" install
}
