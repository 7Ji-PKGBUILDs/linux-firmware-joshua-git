# Maintainer: Jat-Faan Wong
# Contributor: Joshua Riek

pkgname=linux-firmware-joshua-git
pkgver=20240126.e60ff15
pkgrel=1
pkgdesc="Firmware files for Linux - RK3588 specific firmware, with patches of joshua"
arch=('aarch64')
makedepends=('git')
url="https://github.com/Joshua-Riek/firmware"
license=('GPL2' 'GPL3' 'custom')
conflicts=('linux-firmware'{,-orangepi})
provides=('linux-firmware'{,-joshua}="${pkgver}")
options=(!strip)
source=(
  "git+${url}.git"
)

sha256sums=(
  'SKIP'
)

pkgver() {
  cd firmware

  # Commit date + short rev
  echo $(TZ=UTC git show -s --pretty=%cd --date=format-local:%Y%m%d HEAD).$(git rev-parse --short HEAD)
}

package() {
  install -d -m 755 "${pkgdir}"/usr/lib/firmware
  cp -rva "${srcdir}"/firmware/* "${pkgdir}"/usr/lib/firmware
}
