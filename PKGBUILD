# Maintainer: Christian Hesse <mail@eworm.de>

pkgname=libykneomgr
pkgver=0.1.7
pkgrel=1
pkgdesc="Yubico YubiKey NEO Manager C Library"
arch=('i686' 'x86_64')
url="https://github.com/Yubico/libykneomgr"
license=('BSD')
depends=('pcsclite' 'ccid' 'libzip')
conflicts=('libykneomgr-git')
makedepends=('git' 'gengetopt' 'help2man')
source=("git://github.com/Yubico/libykneomgr.git#tag=libykneomgr-${pkgver}")
sha256sums=('SKIP')

build() {
	cd libykneomgr/

	touch ChangeLog
	autoreconf -fi
	./configure --prefix=/usr
	make
}

check() {
	cd libykneomgr/

	make check
}

package() {
	cd libykneomgr/

	install -D -m0644 COPYING "${pkgdir}/usr/share/licenses/libykneomgr/COPYING"
	install -D -m0644 README "${pkgdir}/usr/share/doc/libykneomgr/README"
	make DESTDIR="${pkgdir}/" install
}

