pkgname=python-build
pkgver=1.3.0
pkgrel=2
pkgdesc="A simple, correct PEP 517 build frontend"
arch=('x86_64')
url="https://pypi.org/project/build/"
license=('MIT')
depends=(
    'python-packaging'
    'python-pyproject-hooks'
)
makedepends=(
    'python-build'
    'python-flit-core'
    'python-installer'
)
source=(https://github.com/pypa/build/archive/${pkgver}/${pkgname#*-}-${pkgver}.tar.gz)
sha256sums=(fd7a275d4b34e2b5b4c73fb57ae3c8239b54e4d09752eb540d4167c77bfa043d)

prepare() {
    cd ${pkgname#*-}-${pkgver}

    python3 -m build --wheel --skip-dependency-check --no-isolation
}

package() {
    cd ${pkgname#*-}-${pkgver}

    python3 -m installer -d ${pkgdir} dist/*.whl
}
