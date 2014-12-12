# Contributor: Tirip <tirip01 at yahoo.com>
# Maintainer: Tirip  <tirip01 at yahoo.com>

pkgname=mendeleydesktop
pkgver=1.12.4
pkgrel=1
pkgdesc="Academic software for managing and sharing research papers (desktop client)"
arch=('i686' 'x86_64')
url='http://http://www.mendeley.com/'
license=(custom:mendeley_eula)
depends=(qtwebkit python)
provides=('mendeleydesktop')
install=mendeleydesktop.install

source=("http://www.mendeley.com/client/get/100-2/$pkgname-$pkgver-linux-$CARCH.tar.bz2")
sha256sums=('958ab1f6a2afe2eeb08658563e99067fd660b2929c3626de6606cf5d2dcc96e8')

package() {
  mkdir -p "$pkgdir"/usr/{bin,lib}
  mv "$srcdir"/${pkgname}-${pkgver}-linux-x86_64/* "$pkgdir"/usr/
  rm -r "$pkgdir"/usr/lib/qt
  rm "$pkgdir"/usr/INSTALL
  rm "$pkgdir"/usr/README
  mkdir -p "$pkgdir"/usr/share/licenses/mendeleydesktop
  mv "$pkgdir"/usr/LICENSE "$pkgdir"/usr/share/licenses/mendeleydesktop
}
