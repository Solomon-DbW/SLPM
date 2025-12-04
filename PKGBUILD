pkgname=slpm
pkgver=1.0.0
pkgrel=1
pkgdesc="SLPM — SoloLinux Package Manager with enforced distro identity protection"
arch=('any')
license=('GPL3')
depends=('pacman')
provides=('slpm')
conflicts=('slpm')
source=('slpm' 'os-release.sololinux')
sha256sums=('SKIP' 'SKIP')

package() {
    install -Dm755 "$srcdir/slpm" "$pkgdir/usr/bin/slpm"
    install -Dm644 "$srcdir/os-release.sololinux" "$pkgdir/etc/slpm/os-release"
}

