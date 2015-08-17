# Contributor: Jochen Schalanda <jochen+aur@schalanda.name>
# Contributor: Byron Clark <byron@theclarkfamily.name>
pkgname=thrift-python2
pkgver=0.9.1
pkgrel=1
pkgdesc="Python 2 bindings for Thrift, a scalable cross-language services framework for IPC/RPC"
arch=(i686 x86_64)
url="http://thrift.apache.org/"
license=(APACHE)
depends=(zlib libevent openssl python2)
makedepends=(automake autoconf libtool)
optdepends=(
  'thrift-base: for the Thrift compiler'
  'vim-thrift: for syntax highlighting in vim')
options=(!emptydirs !makeflags)
source=(http://www.apache.org/dist/thrift/$pkgver/thrift-$pkgver.tar.gz)
md5sums=('d2e46148f6e800a9492dbd848c66ab6e')

build() {
  cd $srcdir/thrift-$pkgver

  PYTHON=/usr/bin/python2 ./configure --prefix=/usr \
    --without-cpp \
    --without-qt4 \
    --without-c_glib \
    --without-csharp \
    --without-java \
    --without-erlang \
    --without-perl \
    --without-php \
    --without-php_extension \
    --with-python \
    --without-ruby \
    --without-haskell \
    --without-go \
    --without-d

  make
}

package() {
  cd $srcdir/thrift-$pkgver
  make DESTDIR=$pkgdir install
  rm -r $pkgdir/usr/bin
}

# vim:set ts=2 sw=2 et:
