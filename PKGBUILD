# Maintainer: linuxSEAT <--put_my_name_here--@gmail.com>
# Contributor: Le_J <clej37 at gmail dot com>

pkgname=qtikz
pkgver=0.10
pkgrel=3
pkgdesc="A small application helping you to create TikZ diagrams (from the LaTeX pgf package)"
arch=('i686' 'x86_64')
url="http://www.hackenberger.at/blog/ktikz-editor-for-the-tikz-language/"
license=('GPL')
depends=('poppler-qt' 'shared-mime-info')
provides=('ktikz')
conflicts=('ktikz')
install=${pkgname}.install
source=("http://archive.ubuntu.com/ubuntu/pool/universe/k/ktikz/ktikz_${pkgver}.orig.tar.gz")
md5sums=('e8f0826cba2447250bcdcd389a71a2ac')

prepare() {
    cd $srcdir/ktikz
    sed -i 's/^#\(QC.*or\)/\1-qt4/' conf.pri || return 1
}

build() {
    cd $srcdir/ktikz
    qmake-qt4 PREFIX=/usr || return 1
    make || return 1
}

package() {
    cd $srcdir/ktikz
    make INSTALL_ROOT="$pkgdir" install || return 1 
}
