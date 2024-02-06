# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Pellegrino Prevete <cGVsbGVncmlub3ByZXZldGVAZ21haWwuY29tCg== | base -d>
# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Filipe Laíns (FFY00) <lains@archlinux.org>

_py="python"
_pkg="sphinx"
_pkgname="${_pkg}-inline-tabs"
pkgname="${_py}-${_pkgname}"
pkgver=2023.04.21
pkgrel=1
pkgdesc='Add inline tabbed content to your Sphinx documentation'
arch=(
  'any'
)
url="https://github.com/pradyunsg/${_pkgname}"
license=(
  'MIT'
)
depends=(
  "${_py}-${_pkg}"
)
makedepends=(
  "${_py}-build"
  "${_py}-installer"
  "${_py}-flit-core"
)
source=(
  "${pkgname}-${pkgver}.tar.gz::${url}/archive/${pkgver}.tar.gz"
)
sha512sums=(
  'cad9ccdbf820c69b1f729d6c44ce34ec6005b5a72819f18aff0bf2a02aab66162c51f6a00119c95bddbea39363ce42ead502dc2526013785cb98e3b21965de7d'
)

build() {
  cd \
    "${_pkgname}-${pkgver}"
  "${_py}" \
    -m build \
    --wheel \
    --no-isolation
}

package() {
  cd \
    "${_pkgname}-${pkgver}"
  "${_py}" \
    -m \
      installer \
    --destdir="${pkgdir}" \
    dist/*.whl
  install \
    -Dm 644 \
    LICENSE \
    "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}

# vim:set sw=2 sts=-1 et:
