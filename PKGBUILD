# Maintainer: Rasmus Steinke <rasi at xssn dot at>
pkgname=dmenu-xft-transparency
pkgver=4.5
pkgrel=1
pkgdesc="Dynamic X menu - with xft support and transparency"
url="http://tools.suckless.org/dmenu/"
arch=('i686' 'x86_64')
license=('MIT')
depends=('sh' 'libxinerama' 'libxft')
conflicts=('dmenu')
provides=('dmenu' 'dmenu-xft')
source=(http://dl.suckless.org/tools/dmenu-$pkgver.tar.gz
        dmenu-4.5-xft.diff
        trans.diff)
md5sums=('9c46169ed703732ec52ed946c27d84b4'
         '0c73d595eb78f159bea83f33bba15e80'
         'fdd8e67e0417cdf72f0e25b401125d52')
build() {
	cd $srcdir/dmenu-$pkgver
	patch -p1 < ../dmenu-$pkgver-xft.diff 
    patch -p1 < ../../trans.diff
    cd $srcdir/dmenu-$pkgver
	make 
}
package()
{
    cd "$srcdir/dmenu-$pkgver"
    make DESTDIR=$pkgdir PREFIX=/usr install 
    install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"

}

