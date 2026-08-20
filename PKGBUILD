# Maintainer: Saeed Badreldin <helwanlinux@gmail.org>

pkgname=kazam
pkgver=2.0.0
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

source=("git+https://github.com/helwan-linux/kazam.git")
sha256sums=('SKIP')

build() {
    cd "${srcdir}/${pkgname}"

    python setup.py build
}
package() {
    cd "${srcdir}/${pkgname}"

    python setup.py install \
        --root="${pkgdir}" \
        --optimize=1 \
        --skip-build

    # نسخ ملف الـ desktop
    install -Dm644 data/kazam.desktop "${pkgdir}/usr/share/applications/kazam.desktop"

    # نسخ الأيقونة
    install -Dm644 data/icons/128x128/apps/kazam.png "${pkgdir}/usr/share/icons/hicolor/128x128/apps/kazam.png"
    
    # نسخ ملف الواجهة والصورة مباشرة من مجلد البناء
    install -Dm644 data/ui/kazam.ui "$pkgdir/usr/share/kazam/ui/kazam.ui"
    install -Dm644 data/ui/hl.png "$pkgdir/usr/share/kazam/ui/hl.png"
}
