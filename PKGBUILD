# Contributor: Martin Stolpe <martinstolpe <at> googlemail dot com>
# Contributor: rtfreedman  (rob<d0t>til<d0t>freedman<aT>googlemail<d0t>com

pkgname=bpmdj
pkgver=v4.2_pl4
pkgrel=4
pkgdesc="Free Dj tools with a fully automatic BPM counter"
arch=('i686' 'x86_64')
url="http://bpmdj.yellowcouch.org/index.html"
license=('GPL')
depends=('fftw' 'qt4' 'boost')
optdepends=('alsa-lib: for ALSA playback'
  'jack-audio-connection-kit: for JACK playback')

source=("ftp://bpmdj.yellowcouch.org/bpmdj/bpmdj-${pkgver//_/-}.tar.bz2"
    "defines.archlinux64"
    "defines.archlinux")

options=(!makeflags !buildflags)
noextract=(bpmdj-${pkgver//_/-}.tar.bz2)

build() {
  cd "$srcdir"
  mkdir -p "$pkgname-$pkgver"
  tar -xf bpmdj-${pkgver//_/-}.tar.bz2 -C "$pkgname-$pkgver"

  cd "$pkgname-$pkgver"

  if [ "$CARCH" = "i686" ]; then
    cat ../defines.archlinux >defines
  elif [ "$CARCH" = "x86_64" ]; then
    cat ../defines.archlinux64 >defines
  fi
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  mkdir -p "${pkgdir}"/usr/bin
  #  idx2txt
  cp bpmdj bpmplay bpmmerge bpmcount bpmdjraw "${pkgdir}"/usr/bin
  # docs
  mkdir -p "${pkgdir}"/usr/share/doc/$pkgname
  cp authors.txt changelog.txt readme.txt support.txt "${pkgdir}"/usr/share/doc/$pkgname
}

#[Desktop Entry]
#Name=BpmDJ - Free Dj Tools
#Comment=Free Dj tools with a fully automatic BPM counter
#Type=Application
#Exec=bpmdj
#Icon=bpmdj
#Encoding=UTF-8
#Categories=AudioVideo;Player;

#bpmdj-v4.2_pl3/bpmdj-12.png
#bpmdj-v4.2_pl3/bpmdj-24.png
#bpmdj-v4.2_pl3/bpmdj-36.png
#bpmdj-v4.2_pl3/bpmdj-48.png
#bpmdj-v4.2_pl3/bpmdj-64.png
#bpmdj-v4.2_pl3/bpmdj-96.png


sha256sums=('3b2fe27d91d0e728edcd9a8b1803b3b7ee621f6d6da51cad58ceababb40ddff3'
            'd28c5fa681cd99e92c5664224cd15f9cce14056b5c9d9249218319f9e0cc1ac2'
            '0720362e44e757efcc346ca47d3013941c0827dc7608246cfa8dd25f427a02d5')
