# Maintainer: Francois Garillot <francois[@]garillot.net>
# Contributor: György Balló <ballogy@freestart.hu>
pkgname=python2-flickrapi
_pkgname=flickrapi
pkgver=1.4.2
pkgrel=1
pkgdesc="The official Python interface to the Flickr API"
arch=('any')
url="http://stuvel.eu/flickrapi"
license=('Python')
depends=('python2')
makedepends=('docutils')
source=(http://pypi.python.org/packages/source/f/$_pkgname/$_pkgname-$pkgver.zip)
md5sums=('90dca08a45968b18da0894887f3e59b3')

build() {
  cd "$srcdir/$_pkgname-$pkgver"
  find . -type f | xargs sed -i 's@^#!.*python$@#!/usr/bin/python2@'

  python2 setup.py build
}

package() {
  cd "$srcdir/$_pkgname-$pkgver"

  python2 setup.py install --root=$pkgdir/ --optimize=1

  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
  rm -r "$pkgdir"/usr/{README,LICENSE,UPGRADING}
}
