# Maintainer: Felix Yan <felixonmars@archlinux.org>

pkgbase=python-resolvelib
pkgname=(python-resolvelib python2-resolvelib)
pkgver=0.8.1
pkgrel=1
pkgdesc="Resolve abstract dependencies into concrete ones"
url="https://github.com/sarugaku/resolvelib"
license=('ISC')
arch=('any')
makedepends=('python-setuptools' 'python2-setuptools')
checkdepends=('python-commentjson' 'python-pytest-runner')
source=("$pkgbase-$pkgver.tar.gz::https://github.com/sarugaku/resolvelib/archive/$pkgver.tar.gz")
sha512sums=('bc99d0661f3605d97074066df3c57edec8db40f66111f0d7a23ad88097ba4a162368ab396ef75632d09cd8a76417fbee2554d0cdb2f797795c246d16e7e3b955')

build() {
  cd resolvelib-$pkgver
  python setup.py build
  python2 setup.py build
}

check() {
  cd resolvelib-$pkgver
  python setup.py pytest
}

package_python-resolvelib() {
  depends=('python')

  cd resolvelib-$pkgver
  python setup.py install --root="$pkgdir" --optimize=1

  install -Dm644 LICENSE -t "$pkgdir"/usr/share/licenses/$pkgname/
}

package_python2-resolvelib() {
  depends=('python2')

  cd resolvelib-$pkgver
  python2 setup.py install --root="$pkgdir" --optimize=1

  install -Dm644 LICENSE -t "$pkgdir"/usr/share/licenses/$pkgname/
}
