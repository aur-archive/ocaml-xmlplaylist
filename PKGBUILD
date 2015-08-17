# Maintainer: Charles E. Hawkins <charlesthehawk at yahoo dot com>
# Contributor: Thomas S Hatch <thatch45 at gmail dot com>
pkgname=ocaml-xmlplaylist
pkgver=0.1.3
pkgrel=1
arch=('i686' 'x86_64')
license=('GPL')
pkgdesc="OCaml libs to manage playlists in xml."
url="http://savonet.sourceforge.net/"
depends=()
makedepends=('ocaml' 'ocaml-findlib' 'ocaml-xmlm')
options=('!strip' '!makeflags')
source=("http://downloads.sourceforge.net/savonet/${pkgname}-${pkgver}.tar.gz")
md5sums=('436267704ed4f1d0ce8bcf1adbb52839')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  ./configure --prefix=/usr
  make all
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  mkdir -p ${pkgdir}$(ocamlfind printconf destdir)
  make \
    OCAMLFIND_DESTDIR=${pkgdir}$(ocamlfind printconf destdir) \
    OCAMLFIND_LDCONF=ignore \
    install
}
