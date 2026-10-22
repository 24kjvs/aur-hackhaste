# Maintainer: Dr. Marcus Roe <nobody@drm.cc>
pkgname=hackhaste
pkgver=0.2
pkgrel=1
pkgdesc="HackHaste keyboard layout"
arch=('any')
license=('MIT')
depends=('xkeyboard-config' 'python')
optdepends=('kbd: Linux console maps')
install=hackhaste.install

source=(
  "https://github.com/24kjvs/HackHaste/releases/download/v${pkgver}/HackHaste-${pkgver}-linux.tar.gz"
)
sha256sums=('188c315fdd1447c7853b83e8095f0f31d9d727ee8024888fb17b43aa3cf2ff08')

package() {
  cd "$srcdir"

  local _pkg="HackHaste-${pkgver}-linux"

  install -Dm644 "${_pkg}/xkb/haha" \
    "$pkgdir/usr/share/xkeyboard-config-2/symbols/haha"

  mkdir -p "$pkgdir/usr/share/kbd/keymaps/i386/hackhaste"
  install -m644 "${_pkg}"/console/*.map "${_pkg}"/console/*.map.gz \
    "$pkgdir/usr/share/kbd/keymaps/i386/hackhaste/"

  install -Dm755 "${_pkg}/register-hackhaste-xkb.py" \
    "$pkgdir/usr/share/hackhaste/register-hackhaste-xkb.py"

  install -Dm644 "${_pkg}/LICENSE" \
    "$pkgdir/usr/share/licenses/hackhaste/LICENSE"
}