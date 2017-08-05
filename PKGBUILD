# Maintainer: Eric Vidal <eric@obarun.org>

pkgname=s6-portable-utils
pkgver=2.2.1.0
pkgrel=1
pkgdesc="A set of tiny general Unix utilities"
arch=(x86_64)
url="http://skarnet.org/software/${pkgname}/"
license=('ISC')
depends=('skalibs' 'execline')
groups=(s6-suite)
conflicts=('s6-portable-utils-git')
source=("$pkgname::git+git://git.skarnet.org/s6-portable-utils#commit=$_commit")
_commit=24c0ba8a7cfbbf761ee3eb2c3ad9a543e9300e3b # tag 2.2.1.0
sha256sums=('SKIP')
validpgpkeys=('6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal

build() {
  cd ${srcdir}/${pkgname}
  ./configure --prefix=/usr \
			  --bindir=/usr/bin \
			  --sbindir=/usr/bin \
			  --datadir=/etc
  make
}

package() {
  cd ${srcdir}/${pkgname}

  DESTDIR=${pkgdir} make install
  install -D -m644 COPYING "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
  
}

# vim:ft=sh ts=2 sw=2 et:
