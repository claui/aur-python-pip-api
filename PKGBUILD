# Maintainer: Claudia Pellegrino <aur ät cpellegrino.de>

pkgname=python-pip-api
pkgver=0.0.25
pkgrel=1
pkgdesc='An unofficial, importable pip API'
arch=('any')
url='https://github.com/di/pip-api'
license=('Apache')
depends=('python-pip')
makedepends=('python-setuptools')
conflicts=('python-pip-api-git')
options=('!strip')
_untagged_commit_hash=7e4d857253e1f4fba3ff699249c94f981704e657
source=("${pkgname}-${pkgver}.tar.gz::https://github.com/di/pip-api/tarball/${_untagged_commit_hash}")
sha512sums=('f4044d84944af5bcb39b88f30d0d4c1fad70e881d93f1a9f6d84d862c34f16fe56b1aa4a9c5e7e347326668cba303d71dc96b47eb74a475ec811f1dd231192fd')
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
