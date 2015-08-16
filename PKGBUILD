# Contributor: Dirk <lowph at lotje com>
# Contributor: vorenon <edelmann.manuel@gmail.com>

pkgname=mounty
pkgver=0.2.1
pkgrel=2
pkgdesc="Mount disk images (iso, img, bin, mdf, nrg) from app indicator or system tray"
arch=(any)
url=https://launchpad.net/mounty
license=(GPL3)
depends=(fuseiso pygtk python2-notify python2-dbus xdg-utils desktop-file-utils)
source=(http://download.learnfree.eu/repository/skss/$pkgname-$pkgver-all.deb)
optdepends=('xfce4-notifyd: XFCE notification support'
            'indicator-applet: app indicator support')
install=mounty.install
sha256sums=('8fd0cc61ddac7353514d4bd8ebb8941b63ebea9bbc380e8313c8b6aac43c46cc')

package()
{
  bsdtar -xf $srcdir/data.tar.gz
  # Default in Arch is python3, mounty needs python2
  sed -i 's/env python/env python2/g' $srcdir/usr/share/$pkgname/mounty.py
  sed -i 's/usr\/bin\/python/usr\/bin\/python2/g' $srcdir/usr/share/$pkgname/diskimage.py
  chown -R root:root $srcdir/usr
  cp -a $srcdir/usr $pkgdir
}

