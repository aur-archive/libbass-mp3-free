# Maintainer: Robert La Spina <rkidlaspina [at] gmail [dot] com>
pkgname=libbass-mp3-free
pkgver=2.4.11
pkgrel=1
pkgdesc="an audio library for use in software on several platforms. (non-MP3 version)"
arch=('i686' 'x86_64')
url="http://www.un4seen.com/bass.html"
license=('custom')
depends=(alsa-lib)
makedepends=(unzip)
provides=(libbass)
source=(http://us.un4seen.com/files/bass24-linux.zip LICENSE)
md5sums=('07cc66370c415f512682d679ec723573'
	 '9ba933735ead25f00741f2e6d3abed05')

#build() {
#
#}

package() {
	mkdir -p $pkgdir/usr/lib/
	mkdir -p $pkgdir/usr/share/licenses/$pkgname
	mkdir -p $pkgdir/usr/share/doc/$pkgname
	mkdir -p $pkgdir/usr/include

	cp $srcdir/LICENSE $pkgdir/usr/share/licenses/$pkgname
	cp $srcdir/bass.chm $pkgdir/usr/share/doc/$pkgname
	cp $srcdir/bass.h $pkgdir/usr/include/
	[ "$CARCH" == i686 ] && install -Dm755 $srcdir/mp3-free/libbass.so $pkgdir/usr/lib/

	[ "$CARCH" == x86_64 ] && install -Dm755 $srcdir/x64/mp3-free/libbass.so $pkgdir/usr/lib/

	chmod -R 644 $pkgdir/usr/share/licenses/$pkgname/LICENSE
	chmod -R 644 $pkgdir/usr/share/doc/$pkgname/bass.chm
	chmod -R 644 $pkgdir/usr/include/bass.h
}
