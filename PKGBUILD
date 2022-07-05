# Maintainer: Sick Codes <info at sick dot codes>
# Maintainer: Christian Hoff <https://github.com/choff>
# Contributor: Tobias Martin <tm-x at gmx dot net>
# Contributer: Mohammad Hisham Sayed <drhishamsayed128@protonmail.com>

pkgname=anbox-modules-dkms
pkgver=5.18
arch="$(uname -r)"
url='https://gitlab.com/liyalinux/anbox-modules-dkms'
pkgrel=2
pkgdesc='Android kernel driver fork by @choff (binder/binderfs & ashmem) in DKMS format, Patched For 5.18 Kernel'
arch=('x86_64' 'aarch64' 'i386')
license=('GPL3')
provides=("${pkgname}")
depends=('dkms' 'make')
makedepends=('git')
source=("git+${url}.git")
sha256sums=('SKIP')
conflicts=(anbox-modules-dkms-git)
install="$pkgname.install"

package() {
  cd "${srcdir}/${pkgname}"
  install -dm755 "${pkgdir}/usr/src/binder-1"
  install -dm755 "${pkgdir}/usr/src/ashmem-1"
  install -dm755 "${pkgdir}/etc/modules-load.d"
  install -dm755 "${pkgdir}/usr/lib/udev/rules.d"
  cp -rf "${srcdir}/${pkgname}/anbox.conf" "${pkgdir}/etc/modules-load.d/"
  cp -rf "${srcdir}/${pkgname}/99-anbox.rules" "${pkgdir}/usr/lib/udev/rules.d/"
  cp -rT "${srcdir}/${pkgname}/binder" "${pkgdir}/usr/src/binder-1/"
  cp -rT "${srcdir}/${pkgname}/ashmem" "${pkgdir}/usr/src/ashmem-1/"
}

# vim:set ts=2 sw=2 et:
