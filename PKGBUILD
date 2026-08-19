# Maintainer: Saeed Badreldin <saeed@helwanlinux.org>
pkgname=kazam
pkgver=1.4.5
pkgrel=1
pkgdesc="A screencast application (Custom Helwan build)"
arch=('any')
url="https://github.com/helwan-linux/kazam"
license=('LGPL')

depends=(
    'python'
    'python-xlib'
    'python-dbus'
    'python-gobject'
    'python-pyxdg'
    'python-cairo'
    'python-distro'
    'gstreamer'
    'gst-plugins-good'
    'gst-plugins-bad'
    'pulseaudio'
)

makedepends=('git' 'python-setuptools')
provides=('kazam')
conflicts=('kazam')
source=("$pkgname::git+$url.git")
sha256sums=('SKIP')

build() {
    cd "$pkgname"
    python setup.py build
}

package() {
    cd "$pkgname"
    python setup.py install --root="$pkgdir" --optimize=1
}
