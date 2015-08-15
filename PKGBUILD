# Contributor: stefan husmann <stefan-husmann@t-online.de>
pkgname=galaxy  
pkgver=2.2
pkgrel=1
pkgdesc="Stellar Simulation"
url="http://www.kornelix.com/galaxy"
arch=('i686' 'x86_64')
license=('GPL3')
depends=('gtk3')
source=("http://www.kornelix.com/uploads/1/3/0/3/13035936/$pkgname-$pkgver.tar.gz")
md5sums=('dd288631c4d58b98fcc2890ee5873278')

build() {
  cd $srcdir/$pkgname-$pkgver
  export PREFIX=/usr
  sed -i 's+xdg-deskto+#xdg-deskto+' Makefile
  make LDFLAGS="-lpthread" 
}
package() {
  cd $srcdir/$pkgname-$pkgver
  install -d $pkgdir/usr/share/applications
  install -Dm644 desktop $pkgdir/usr/share/applications/$pkgname.desktop 
  make DESTDIR=$pkgdir install  
  rm $pkgdir/usr/share/applications/kornelix-$pkgname.desktop
  rm $pkgdir/usr/share/doc/$pkgname/$pkgname.man
}
