# Maintainer: yasuo-ozu <yasuo@ozu.email>

pkgname=cnijfilter2-bin
pkgver=5.00
pkgrel=1
pkgdesc='Canon IJ Printer Driver for Linux, supporting PIXUS MG7530F / MG7530 / MG5630 / iP110, MAXIFY MB5330 / MB5030 / MB2330 / MB2030 / iB4030'
arch=('x86_64')
url='https://cweb.canon.jp/drv-upd/ij-mfp/linux-pd-20142h-500.html'
license=('CUSTOM')
depends=()
optdepends=()
makedepends=(binutils tar)
options=()
_ARCHIVE_NAME="cnijfilter2-5.00-1-deb.tar.gz"
source=("https://gdlp01.c-wss.com/gds/5/0100006265/01/$_ARCHIVE_NAME")
md5sums=('433e5d53041067deb90584397daec07d')

prepare() {
  cd "${srcdir}"
  tar -xzvf "$_ARCHIVE_NAME"
  mv "cnijfilter2-5.00-1-deb/packages/cnijfilter2_5.00-1_amd64.deb" .
  ar x "cnijfilter2_5.00-1_amd64.deb"
  tar -xzvf data.tar.gz
}

package() {
  cp -r "${srcdir}/usr" "${pkgdir}/"
  mkdir -p "${pkgdir}/usr/share/licenses/${pkgname}"
  install -Dm644 "${srcdir}/usr/share/doc/cnijfilter2/LICENSE-cnijfilter-5.00EN.txt"  "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
