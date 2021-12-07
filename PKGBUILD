# Contributor: Erik Inkinen <erik.inkinen@gmail.com>

pkgname=ofono2mm
provides=('ofono2mm')
pkgver=0.1
pkgrel=1
pkgdesc="A simple Python script implementing ModemManager D-Bus API and using oFono to manage the modems."
arch=('any')
url="https://github.com/droidian/oFono2MM"
license=('GPL2')
depends=('ofono' 'modemmanager' 'python-dbus-next')
makedepends=('git')
source=('oFono2MM::git+https://github.com/droidian/oFono2MM.git')
md5sums=('SKIP')

package() {
    cd oFono2MM

    install -d ${pkgdir}/usr/lib/ofono2mm/ofono2mm
    install -m 755 main.py ${pkgdir}/usr/lib/ofono2mm/
    install -m 644 ofono2mm/* ${pkgdir}/usr/lib/ofono2mm/ofono2mm
    install -m 644 *.xml ${pkgdir}/usr/lib/ofono2mm/

    install -d ${pkgdir}/usr/bin
    ln -s /usr/lib/ofono2mm/main.py ${pkgdir}/usr/bin/ofono2mm

    install -d ${pkgdir}/etc/systemd/system/ModemManager.service.d
    install -m 644 systemd/10-ofono2mm.conf ${pkgdir}/etc/systemd/system/ModemManager.service.d/
}
