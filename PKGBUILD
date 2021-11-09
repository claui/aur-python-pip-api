# Maintainer: Claudia Pellegrino <aur ät cpellegrino.de>

pkgname=python-pip-api
pkgver=0.0.23
pkgrel=1
pkgdesc='An unofficial, importable pip API'
arch=('any')
url='https://github.com/di/pip-api'
license=('Apache')
depends=('python-pip')
makedepends=('python-setuptools')
conflicts=('python-pip-api-git')
options=('!strip')
source=("${pkgname}-${pkgver}.tar.gz::https://github.com/di/pip-api/archive/refs/tags/${pkgver}.tar.gz")
sha512sums=('de2016a3f283831d893a26d9e29b6f33415a64facc1862028a39593fbc6a83c3f0a859fed1bd6d5eb2a8c211e504d3a2cc34e6c2b204d7135646cbd90e8a1ed0')

build() {
  cd "${srcdir}/${pkgname#python-}-${pkgver}"
  python setup.py build
}

package() {
  cd "${srcdir}/${pkgname#python-}-${pkgver}"
  python setup.py install --root="$pkgdir" --optimize=1
}
