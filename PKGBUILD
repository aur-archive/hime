# $Id$
# Maintainer: taylorchu <tailinchu@gmail.com>
# arch PKGBUILD template

pkgname=hime
pkgver=20120129
pkgrel=1
pkgdesc='An universal input method platform'
url='http://hime.luna.com.tw'
license=('LGPL')
arch=('i686' 'x86_64')
depends=('gtk2' 'libxtst' 'libchewing')
makedepends=('git' 'libchewing')
optdepends=('libchewing: support for chewing input method')

install=install

_gitroot="https://github.com/caleb-/hime"
_gitname="hime"
build() {
   cd "$srcdir"
 msg "Connecting to GIT server...."
 if [ -d $_gitname ] ; then
   cd $_gitname && git pull origin
   msg "The local files are updated."
 else
   git clone --depth=1 $_gitroot $_gitname
   cd $_gitname
 fi
 msg "GIT checkout done or server timeout"
 ./configure --prefix=/usr --qt4-moc-path=/usr/bin/moc --qt4-im-module-path=/usr/lib/qt/plugins/inputmethods
 make
 make DESTDIR="$pkgdir" install
}
