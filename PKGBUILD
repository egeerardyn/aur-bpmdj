# Maintainer: Egon Geerardyn <egon <dot> geerardyn <at> gmail <dot> com>
# Contributor: Martin Stolpe <martinstolpe <at> googlemail dot com>
#you need to have at least alsa, oss or jack to be installed on the system
pkgname=bpmdj
pkgver=4.2_pl3
pkgrel=1
pkgdesc="Tool for detecting the BPM of mp3, ogg, m4a, mpc and flac files"
arch=('i686' 'x86_64')
url="http://bpmdj.yellowcouch.org/index.html"
license=('GPL')
depends=('fftw' 'openssl' 'qt')
makedepends=('cmake' 'gcc')
optdepends=('alsa-lib: for ALSA playback'
  'jack-audio-connection-kit: for JACK playback')
source=(ftp://bpmdj.yellowcouch.org/bpmdj/$pkgname-v${pkgver//_/-}.tar.bz2
defines.arch
)


build() {
  cd "$srcdir"
  cp defines.arch $srcdir/defines
#  [ -d "${srcdir}/build" ] && rm -rf "${srcdir}/build"
  
#  rm "${srcdir}/version.h"
#  rm "${srcdir}/data-syntax.cpp"
#  rm "${srcdir}/data-lexer.cpp"

#  mkdir -p "${srcdir}/build" || return 1
#  cd "${srcdir}/build"
#  cmake ../ -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE=Release
  make

  make DESTDIR="$pkgdir/" install
}
#md5sums=('e2590f2c6b2bd6074438faab9ca547e1')
