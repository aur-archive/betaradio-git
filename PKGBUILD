# Contributor : Yanganto <yanganto@gmail.com>
# Contributor : Daniel YC Lin <dlin.tw at gmail>
# Maintainer : Louie Chen <louie23 at gmail>

pkgname=betaradio-git
pkgver=1.6.r12.g0a482d6
pkgrel=6
arch=('i686' 'x86_64')
license=('GPL3')
pkgdesc="An easy way to listen to internet radio of Taiwan."
url="https://github.com/fourdollars/betaradio"
depends=('gtk3' 'json-glib' 'libsoup' 'libltdl' 'gstreamer' 'gst-plugins-good' 'gst-plugins-bad' 'gst-plugins-ugly' 'gst-libav' 'openal' )
#'gstreamer0.10' 'hicolor-icon-theme')
#optdepends=('gstreamer0.10-plugins')
makedepends=('git'  'vala')
conflicts=(betaradio)
source=('repo::git+https://github.com/fourdollars/betaradio.git')
md5sums=('SKIP')
install=betaradio.install

pkgver() {
  cd repo
  git describe --long --tags | sed -r 's/([^-]*-g)/r\1/;s/-/./g'
}

build() {
  cd repo
  ./autogen.sh
  ./configure --prefix=$pkgdir/usr
  make
}

package() {
  cd repo
  make install
  rmdir $pkgdir/usr/lib $pkgdir/usr/include
}
# vim:et sw=2 ts=2 ai
