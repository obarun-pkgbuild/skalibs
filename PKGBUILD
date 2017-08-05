# Maintainer: Eric Vidal <eric@obarun.org>

pkgname=skalibs
pkgver=2.5.1.1
pkgrel=1
pkgdesc="A general-purpose low-level C library"
arch=(x86_64)
url="http://www.skarnet.org/software/skalibs/"
license=('ISC')
groups=(s6-suite)
makedepends=('git')
conflicts=('skalibs-git')
source=("$pkgname::git+git://git.skarnet.org/skalibs#commit=$_commit")
_commit=4a554eb0b9e9a95ccd22723e3fc72908b6902a06 # tag 2.5.1.1
md5sums=('SKIP')
validpgpkeys=('6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal

build() {
  cd "$srcdir/$pkgname"
  ./configure	--prefix=/usr \
				--enable-force-devr \
				--with-default-path=/usr/local/bin:/usr/bin
				
  make
}

package() {
  cd "$srcdir/$pkgname"
  make DESTDIR="$pkgdir/" install
  install -Dm644 COPYING $pkgdir/usr/share/licenses/$pkgname/COPYING
} 
