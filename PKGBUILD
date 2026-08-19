# Maintainer: Saeed Badreldin <helwanlinux@gmail.org>

pkgname=kazam
pkgver=1.4.5
pkgrel=1
pkgdesc="Simple desktop recording and screenshot tool"
arch=('any')
url="https://launchpad.net/kazam"
license=('GPL3')

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

makedepends=(
    'python-setuptools'
)

source=(
    "https://launchpad.net/kazam/1.4/1.4.5/+download/kazam-${pkgver}.tar.gz"
)

sha256sums=('SKIP')

build() {
    cd "${srcdir}/${pkgname}-${pkgver}"

    python setup.py build
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}"

    python setup.py install \
        --root="${pkgdir}" \
        --optimize=1 \
        --skip-build
}
