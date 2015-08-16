# Maintainer : Martin Wimpress <code@flexion.org>
# Contributor: Giovanni Ricciardi <kar98k.sniper@gmail.com>
# Contributor: Xpander <xpander0@gmail.com>

pkgname=mate-sensors-applet
pkgver=1.6.1
pkgrel=1
pkgdesc="A MATE Panel applet to display readings from hardware sensors, including CPU temperature, fan speeds and voltage readings."
url="http://mate-desktop.org"
arch=('i686' 'x86_64')
license=('GPL')
depends=('dbus' 'gtk2' 'libatasmart' 'libnotify' 'libxnvctrl' 'lm_sensors' 'mate-panel' )
makedepends=('docbook-xml' 'mate-common' 'mate-doc-utils' 'perl-xml-parser' 'rarian')
options=('!emptydirs')
groups=('mate-extra')
source=("http://pub.mate-desktop.org/releases/1.6/${pkgname}-${pkgver}.tar.xz")
sha1sums=('3b57d8e4b47ff2b25bbcee465c0ef7c37bcff1f7')
install=${pkgname}.install

build() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    ./configure \
        --prefix=/usr \
        --libexecdir=/usr/lib/${pkgname} \
        --disable-static \
        --disable-scrollkeeper
  make
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    make DESTDIR="${pkgdir}" install
}
