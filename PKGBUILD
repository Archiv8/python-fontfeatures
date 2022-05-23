#!/bin/bash

# Created from the original PKGBUILD by Caleb Maclennan <caleb@alerque.com>

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Ross Clark <https://github.com/Archiv8/python-pyclipper/discussions>
# Contributor: Ross Clark <https://github.com/Archiv8/python-pyclipper/discussions># Maintainer: Caleb Maclennan <caleb@alerque.com>

_langname="python"
_relname="fontFeatures"
_pacname="fontfeatures"

pkgname="${_langname}-${_pacname}"
pkgver=1.6.4
pkgrel=1
pkgdesc="Library for manipulating OpenType font features"
arch=(
  "any"
)
url="https://github.com/simoncozens/fontfeatures"
license=(
  "MIT"
)
depends=(
  "python"
  "python-beziers"
  "python-fs"
  "python-fonttools"
  "python-lxml"
)
makedepends=(
  "python-build"
  "python-installer"
  "python-setuptools"
  "python-wheel"
  )
optdepends=(
  "python-glyphtools"
  )
_tarname="${_relname}-${pkgver}"
source=(
  "https://files.pythonhosted.org/packages/source/${_relname::1}/${_relname}/${_tarname}.tar.gz")
sha512sums=(
  "113e2247da30729dc15ba17f9aab62c15e8be616ec64f9218000e20a1b9cf66f0b55632c5ba93b84b487abd9f3517bb7ee31f7f723baf0003ea401157e9c1cfd"
  )

build() {

  cd "${_tarname}"

  python -m build -wn
}

package() {

  cd "${_tarname}"

  python -m installer -d "${pkgdir}" dist/*.whl

  install -Dm0644 -t "${pkgdir}/usr/share/licenses/${pkgname}/" LICENSE
}
