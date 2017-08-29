# Maintainer: Eric Vidal <eric@obarun.org>

pkgname=skalibs
pkgver=2.6.0.0
pkgrel=1
pkgdesc="A general-purpose low-level C library"
arch=(x86_64)
url="http://www.skarnet.org/software/skalibs/"
license=('ISC')
groups=(s6-suite)
makedepends=('git')
conflicts=('skalibs-git')
source=("$pkgname::git+git://git.skarnet.org/skalibs#commit=$_commit")
_commit=72de81e772b1c3a350c8265752ef91bab52741d1 # tag 2.6.0.0
md5sums=('SKIP')
validpgpkeys=('6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal

build() {
  cd "$srcdir/$pkgname"
  ./configure	--prefix=/usr \
				--with-default-path=/usr/local/bin:/usr/bin
				
  make
}

package() {
  cd "$srcdir/$pkgname"
  make DESTDIR="$pkgdir/" install
  
  # add doc
  install -dm 0755 $pkgdir/usr/share/doc/$pkgname/
  cp -R doc/* $pkgdir/usr/share/doc/$pkgname/
  
  install -Dm644 COPYING $pkgdir/usr/share/licenses/$pkgname/COPYING
} 
