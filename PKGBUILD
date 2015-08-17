# Maintainer: Attila Bukor <r1pp3rj4ck [at] w4it [dot] eu>
# Contributor: Hugo Osvaldo Barrera <hugo@barrera.io>
# Contributor: xantares <xantares09@hotmail.com>
# Contributor: Eric Engestrom <aur [at] engestrom [dot] ch>
# Contributor: Iwan Timmer <irtimmer@gmail.com>
# Contributor: Ricardo Band <me [at] xengi [dot] de>

pkgname=popcorntime-working
pkgver=0.3.7.2
pkgrel=12
pkgdesc="Downloads popcorntime from the popcorntime.io page and then installs it to /usr/share.popcorntime . Unlike the popcorntime package, this means that you don't have to install any dependencies or compile anything. Happy watching!"
arch=('x86_64' 'i686')
url="http://popcorntime.io"
_upstream="http://104.131.187.115/build/Popcorn-Time-0.3.7.2-Linux64.tar.xz"
if [ "$CARCH" = 'i686' ]; then
	_upstream="http://104.131.187.115/build/Popcorn-Time-0.3.7.2-Linux32.tar.xz"
fi
license=('GPL3')
makedepends=('sudo' 'curl' 'tar')
depends=('ttf-ms-fonts')
install="popcorntime.install"
conflicts=('popcorntime' 'popcorntime-bin' 'popcorntime-git')
sources=('popcorntime.install')

build() {
	mkdir -p /tmp/popcorntime
	cd /tmp/popcorntime
	echo "In /tmp/popcorntime and going to curl the tarball"
	curl -L $_upstream > tarball.tar.xz
	echo "Going to extract it"
	tar -xf tarball.tar.xz
	echo "Success"
	echo "Removing tarball"
	rm tarball.tar.xz
}

package() {
	cd /tmp
	echo "In /tmp/popcorntime and copying to /usr/share/popcorntime"
	sudo mkdir -p /usr/share/popcorntime
	sudo install -m755 popcorntime/* /usr/share/popcorntime
	echo "Installation complete. Now linking to bin"
	echo "Done"
}
