# Maintainer: Johannes Schleifenbaum <johannes [at] js-webcoding [dot] de>
# Contributor: Attila Bukor <r1pp3rj4ck [at] w4it [dot] eu>
# Please report issues at https://github.com/jojosch/pkgbuilds

pkgname=php-box
pkgver=2.6.1
pkgrel=1
pkgdesc="An application for building and managing Phars"
url="https://github.com/box-project/box2"
license=("MIT")
arch=("any")
depends=("php>=5.3.3")
install="${pkgname}.install"
source=(
  "https://github.com/box-project/box2/releases/download/${pkgver}/box-${pkgver}.phar"
  "https://raw.github.com/box-project/box2/${pkgver}/LICENSE"
)
sha256sums=(
  "abdadc1b1c79a60ac8aade62d9eea705d9a4bb69ea0e31e4592e6eb9489cb357"
  "ba2dfc30b9659262549c839894838d9a1fe78ca533d0338cebc2f4f634b3bb12"
)

package() {
  install -D -m644 "${srcdir}/LICENSE" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
  install -D -m755 "${srcdir}/box-${pkgver}.phar" "${pkgdir}/usr/share/webapps/bin/${pkgname}.phar"
  install -d "${pkgdir}/usr/bin"
  ln -s "/usr/share/webapps/bin/${pkgname}.phar" "${pkgdir}/usr/bin/${pkgname}"
}
