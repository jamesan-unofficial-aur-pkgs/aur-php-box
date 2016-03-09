# Maintainer: Johannes Schleifenbaum <johannes [at] js-webcoding [dot] de>
# Contributor: Attila Bukor <r1pp3rj4ck [at] w4it [dot] eu>
# Please report issues at https://github.com/jojosch/pkgbuilds

pkgname=php-box
_pkgname=${pkgname#php-}
pkgver=2.6.1
pkgrel=2
pkgdesc="An application for building and managing Phars"
url="https://github.com/box-project/box2"
license=("MIT")
arch=("any")
depends=("php>=5.3.3")
install="${pkgname}.install"
source=(
  "https://github.com/box-project/box2/releases/download/${pkgver}/${_pkgname}-${pkgver}.phar"
  "https://raw.github.com/box-project/box2/${pkgver}/LICENSE"
  phar.ini
)
sha256sums=('abdadc1b1c79a60ac8aade62d9eea705d9a4bb69ea0e31e4592e6eb9489cb357'
            'ba2dfc30b9659262549c839894838d9a1fe78ca533d0338cebc2f4f634b3bb12'
            'bcbd83e1fc62e9bb0702cf5e6c839f8984e8451300da913060106d01275546db')

package() {
  install -D -m644 "${srcdir}/phar.ini" "${pkgdir}/etc/php/conf.d/phar.ini"
  install -D -m644 "${srcdir}/LICENSE" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
  install -D -m755 "${srcdir}/${_pkgname}-${pkgver}.phar" "${pkgdir}/usr/share/webapps/bin/${_pkgname}.phar"
  install -d "${pkgdir}/usr/bin"
  ln -s "/usr/share/webapps/bin/${_pkgname}.phar" "${pkgdir}/usr/bin/${_pkgname}"
}
