pkgname=sayonara-player
pkgver=20160222.2cf310e
_pkgver=0.8.2-git1-20160219
pkgrel=1
pkgdesc="Is a small, clear and fast audio player for Linux written in C++, supported by the Qt framework. It uses Gstreamer as audio backend."
arch=( 'x86_64')
url="http://sayonara-player.com"
license=('GPL3')
depends=('qt5-base' 'taglib' 'gst-plugins-base' 'gst-plugins-good' 'gst-plugins-bad' 'libmtp')
optdepends=('lame' 'gst-plugins-ugly')
makedepends=('cmake' 'qt5-tools')
source=("$pkgname::git+https://git.sayonara-player.com/sayonara.git")
md5sums=('SKIP')


pkgver() {
    cd "${srcdir}/${pkgname}"
    git log -1 --format='%cd.%h' --date=short | tr -d -
}

build() {
        cd "$srcdir/$pkgname"
    mkdir build
    cd build
        cmake .. -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE="Release"
        make
}

package() {
        cd "$srcdir/$pkgname"
    cd build
        make DESTDIR="$pkgdir/" install
}



