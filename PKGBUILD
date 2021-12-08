# Maintainer: Claudia Pellegrino <aur ät cpellegrino.de>

pkgname=python-pip-api
pkgver=0.0.26
pkgrel=1
pkgdesc='An unofficial, importable pip API'
arch=('any')
url='https://github.com/di/pip-api'
license=('Apache')
depends=('python-pip')
makedepends=('python-setuptools')
conflicts=('python-pip-api-git')
options=('!strip')
_untagged_commit_hash='c0707e9bca9361a77a1a3c748d327f76e912602c'
source=("${pkgname}-${pkgver}.tar.gz::https://github.com/di/pip-api/tarball/${_untagged_commit_hash}")
sha512sums=('a130c5aefcacae68e939a8b7b481b341dd283febfb851de0705461ae0dd6f6f543689130e106f92aec82fe8b4648f456d62b6656e80733b07080837dfc45faa9')
noextract=("${pkgname}-${pkgver}.tar.gz")

# Strip first component to ease handling untagged commits
prepare() {
  mkdir -p "${srcdir}/${pkgname#python-}-${pkgver}"
  tar -x -f "${srcdir}/${pkgname}-${pkgver}.tar.gz" \
    -C "${srcdir}/${pkgname#python-}-${pkgver}" \
    --strip-components=1
}

build() {
  cd "${srcdir}/${pkgname#python-}-${pkgver}"
  python setup.py build
}

package() {
  cd "${srcdir}/${pkgname#python-}-${pkgver}"
  python setup.py install --root="$pkgdir" --optimize=1
}
