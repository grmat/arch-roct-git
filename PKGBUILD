# Maintainer: grmat <grmat@sub.red>

pkgname=roc-roct-git
_pkgname=ROCT-Thunk-Interface
pkgdesc='Radeon Open Compute Thunk Interface'
pkgver=1.5.0.r0.gf27b70a
pkgrel=1
arch=('x86_64')
license=('MIT')
makedepends=('git')
depends=('')

source=("git+https://github.com/RadeonOpenCompute/${_pkgname}.git")
sha256sums=('SKIP')

pkgver() {
  cd $srcdir/${_pkgname}
  git describe --long | sed 's/^roc-//;s/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
  cd ${srcdir}/${_pkgname}/src
  make ${MAKEFLAGS} package-common
}

package() {
  mv ${srcdir}/${_pkgname}/build/package-common/libhsakmt/opt ${pkgdir}
  cd ${srcdir}/${_pkgname}
  make clean
}
