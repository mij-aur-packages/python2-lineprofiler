# Maintainer: lestb <tkhdlstfl dot l plus aur at gmail dot com>
# Contributor: Sebastien Binet <binet@lblbox>
# Package Repository: https://github.com/mij-aur-packages/python2-lineprofiler
pkgname=python2-lineprofiler
pkgver=2.1.2
pkgrel=1
pkgdesc="Line-by-line profiler."
url="http://pypi.python.org/pypi/line_profiler"
arch=('i686' 'x86_64')
license=('BSD')
depends=( 'python2' 'ipython2')
makedepends=('cython2')
source=(https://pypi.python.org/packages/source/l/line_profiler/line_profiler-$pkgver.tar.gz)
sha256sums=('efa66e9e3045aa7cb1dd4bf0106e07dec9f80bc781a993fbaf8162a36c20af5c')

build() {
  cd "${srcdir}/line_profiler-${pkgver}"
  python2 setup.py build
}

package() {
  license_dir="${pkgdir}/usr/share/licenses/${pkgname}"
  cd "${srcdir}/line_profiler-${pkgver}"
  python2 setup.py install --prefix=/usr --root="${pkgdir}"
  install -d ${license_dir}
  install -m644 LICENSE{,_Python}.txt "${license_dir}"
  mv "${pkgdir}"/usr/bin/kernprof{,2}
}
