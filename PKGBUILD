# Maintainer: zqzhao5 <zqzhao5@gmail.com>
pkgname=youdao
pkgver=1.0.2
pkgrel=1
pkgdesc="有道官方词典"
arch=(x86_64)
url="http://cidian.youdao.com/index-linux.html?keyfrom=cnbeta"
license=('GPL')
depends=('python' 'python-pyqt5' 'python-requests' 'python-xlib' 'python-lxml' 'qt5-quickcontrols' 'qt5-graphicaleffects' 'qt5-webkit' 'python-pillow' 'tesseract-data-eng' 'tesseract-data-chi_tra' 'tesseract-data-chi_sim')
source=("http://101.4.136.34:9999/codown.youdao.com/cidian/linux/youdao-dict_1.0.2~binary_amd64.tar.gz")
md5sums=('84c75a7759e9abf97b636b4ffe625bd0')

package() {
   mkdir -p ${pkgdir}/usr/bin
   mkdir -p ${pkgdir}/usr/share/youdao-dict
   mkdir -p ${pkgdir}/usr/share/applications
   mkdir -p ${pkgdir}/usr/share/dbus-1/services
   mkdir -p ${pkgdir}/usr/share/icons/hicolor/48x48/apps
   mkdir -p ${pkgdir}/usr/share/icons/hicolor/scalable/apps
   mkdir -p /etc/xdg/autostart

   cp -r ${srcdir}/src/* ${pkgdir}/usr/share/youdao-dict
   cp -r ${srcdir}/data/hicolor/* ${pkgdir}/usr/share/icons/hicolor/
   cp ${srcdir}/data/youdao-dict.desktop ${pkgdir}/usr/share/applications/
   cp ${srcdir}/data/com.youdao.backend.service ${pkgdir}/usr/share/dbus-1/services/

   chmod 755 ${pkgdir}/usr/share/youdao-dict/main.py
   chmod 755 ${pkgdir}/usr/share/youdao-dict/youdao-dict-backend.py

   BIN_PATH=${pkgdir}/usr/bin/youdao-dict
   [ -e $BIN_PATH ] && rm -f $BIN_PATH
   ln -sf ${pkgdir}/usr/share/youdao-dict/main.py $BIN_PATH
}
