# Maintainer: Claudia Pellegrino <aur ät cpellegrino.de>

pkgname=python-pip-api
pkgver=0.0.30
pkgrel=1
pkgdesc='An unofficial, importable pip API'
arch=('any')
url='https://github.com/di/pip-api'
license=('Apache')
depends=('python-pip')
makedepends=('python-build' 'python-installer' 'python-wheel')
conflicts=('python-pip-api-git')
options=('!strip')
source=("${pkgname}-${pkgver}.tar.gz::https://github.com/di/pip-api/archive/refs/tags/${pkgver}.tar.gz")
sha512sums=('0fa69d55c919f2985c0acfdc719eff0a89ac065df8eca84d518a5ed0bcfb3a79c559002441041ef3382ca60a4d6c8bd991fd71316cd4e4d1643a3e084ed60f89')

build() {
  cd "${srcdir}/${pkgname#python-}-${pkgver}"
  python -m build --wheel --no-isolation
}

package() {
  cd "${srcdir}/${pkgname#python-}-${pkgver}"
  python -I -X pycache_prefix=pycache -m installer \
    --destdir="${pkgdir}" dist/*.whl
  rm -rf pycache
  install -D -m 644 -t "${pkgdir}/usr/share/licenses/${pkgname}" \
    LICENSE
}
