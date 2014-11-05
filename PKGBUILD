# Contributor: Tirip <tirip01 at yahoo.com>
# Maintainer: Tirip  <tirip01 at yahoo.com>

pkgname=mendeleydesktop
pkgver=1.12.2
pkgrel=1
pkgdesc="Academic software for managing and sharing research papers (desktop client)"
arch=('i686' 'x86_64')
url='http://http://www.mendeley.com/'
license=(custom:mendeley_eula)
depends=(qtwebkit python)
provides=('mendeleydesktop')
install=mendeleydesktop.install
#sha256sums=('5484716ec4adf29a7bfc5ecb45c8ed4d6a5e253b8c72fccea12662454d398b85')

if [[ $CARCH == "x86_64" ]]
then
  _arch=x86_64
  sha256sums=('5c62bce08dfb37e8d820192b9fefdd3e5b7452a4080db9410bede2225ddc40ee'
	'bf4c574ac118e0f1347d3b681bcc19d0927872459f3be7ee6fc875c6c7d92ea6')
else
 _arch=i686
  sha256sums=('5c62bce08dfb37e8d820192b9fefdd3e5b7452a4080db9410bede2225ddc40ee'
	'bf4c574ac118e0f1347d3b681bcc19d0927872459f3be7ee6fc875c6c7d92ea6')
  depends+=('lib32-libpng12')
fi
source=("http://www.mendeley.com/client/get/100-2/${pkgname}-${pkgver}-linux-${_arch}.tar.bz2"
	"mendeleydesktop.desktop")

package() {
  mkdir -p "$pkgdir"/usr/{bin,lib}
  mv "$srcdir"/${pkgname}-${pkgver}-linux-${_arch}/* "$pkgdir"/usr/
  rm -r "$pkgdir"/usr/lib/qt
  rm "$pkgdir"/usr/INSTALL
  rm "$pkgdir"/usr/README
  mkdir -p "$pkgdir"/usr/share/licenses/mendeleydesktop
  mv "$pkgdir"/usr/LICENSE "$pkgdir"/usr/share/licenses/mendeleydesktop
  install -Dm644 "$srcdir"/mendeleydesktop.desktop "$pkgdir"/usr/share/applications/mendeleydesktop.desktop
}
