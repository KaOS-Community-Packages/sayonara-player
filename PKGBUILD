pkgname=sayonara-player
_pkgver=1.9.0-stable1
pkgver=${_pkgver//-/_}
pkgrel=1
pkgdesc="Sayonara is a small, clear and fast audio player for Linux written in C++, supported by the Qt framework. It uses Gstreamer as audio backend."
arch=( 'x86_64')
url="http://sayonara-player.com"
license=('GPL3')

depends=(qt5-base taglib gst-plugins-base gst-plugins-good)
makedepends=(git cmake qt5-tools qt5-svg gst-plugins-bad)
optdepends=('gst-libav: additional codecs'
            'gst-plugins-bad: additional codecs'
            'gst-plugins-ugly: additional codecs')

source=("git+https://gitlab.com/luciocarreras/sayonara-player.git#tag=${_pkgver}")
sha512sums=('SKIP')

build() {
cd "$srcdir/$pkgname"
mkdir build
cd build
cmake .. -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE="Release"
make
}

package() {
cd "$srcdir/$pkgname/build"
make DESTDIR="$pkgdir/" install
}
