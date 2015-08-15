# Maintainer: Justin Dray <justin@dray.be>

pkgname=chromium-pepper-flash-armv7h
pkgdesc="Google Chrome's Pepper Flash plugin for Chromium on armv7h"
pkgver=12.0.0.77
pkgrel=1
arch=('armv7h')
url="http://www.google.com/chrome"
license=('custom:chrome')
depends=('chromium')
provides=("chromium-pepper-flash=${pkgver}")
optdepends=('pulseaudio-alsa: For PulseAudio users')
install=chromium-pepper-flash.install
source=(
	'license.html::http://www.google.com/chrome/intl/en/eula_text.html'
	"https://www.dray.be/arch/files/PepperFlash-${pkgver}-armv7h.tar.gz")
md5sums=('ba19ea498f294975d320ff0b26a6cd63'
         '2e12f0a2abed3e34e2bcbed1ff40c61e')

package() {
	install -d "${pkgdir}/usr/lib/PepperFlash"
	install -m644 ${srcdir}/* "${pkgdir}/usr/lib/PepperFlash"
	sed -i "s/flashver=.*/flashver=${pkgver}/" "${startdir}/chromium-pepper-flash.install"
	install -Dm644 "${srcdir}/license.html" "${pkgdir}/usr/share/licenses/${pkgname}/license.html"
}
