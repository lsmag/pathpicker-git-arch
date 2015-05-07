# Maintainer: Lucas Sampaio <lucas@lsmagalhaes.com>

_pkgname=pathpicker
pkgname=${_pkgname}-git
pkgver=0.r87.e060419
pkgrel=1
pkgdesc='Facebook PathPicker is a simple command line tool that solves the perpetual problem of selecting files out of bash output.'
url='https://github.com/facebook/PathPicker'
license=('BSD')
source=('git+https://github.com/facebook/PathPicker.git')
sha256sums=('SKIP')
arch=('any')
makedepends=('git' 'python2')
conflicts=('fpp')
provides=('fpp')

pkgver() {
  cd "${srcdir}/PathPicker"
  printf "0.r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
  mkdir -p $pkgdir/opt/PathPicker
  mv $srcdir/PathPicker $pkgdir/opt

  mkdir -p $pkgdir/usr/bin
  echo "Currently it seems PathPicker has a problem with linux symlinks,"
  echo "so please add '/opt/PathPicker/' to your \$PATH to use fpp"

  # TODO: use symlink
  # ln -s "$pkgdir/opt/PathPicker/fpp" "$pkgdir/usr/bin/fpp"
}
