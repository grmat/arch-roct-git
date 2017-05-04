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
  cd ${srcdir}/${_pkgname}
  make ${MAKEFLAGS} all
}

package() {
  mkdir -p "${pkgdir}/usr/include"
  cp -r "${srcdir}/${_pkgname}/include" "${pkgdir}/usr/include/libhsakmt"

  cd ${srcdir}/${_pkgname}/build/lnx64a
  mkdir -p "${pkgdir}/usr/lib"
  mv "libhsakmt.so" "${pkgdir}/usr/lib/"
  mv "libhsakmt.so.1" "${pkgdir}/usr/lib/"

  cd ${srcdir}/${_pkgname}
  make clean
}
