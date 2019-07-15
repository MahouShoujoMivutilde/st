# Maintainer:

pkgname=st-mivu
_pkgname=st
pkgver=0.8.2.r1090.49bd77d
pkgrel=1
pkgdesc="Simple (suckless) terminal"
url="https://github.com/MahouShoujoMivutilde/st"
arch=('i686' 'x86_64')
license=('MIT')
depends=('libxft')
makedepends=('ncurses' 'libxext' 'git')
optdepends=('dmenu: feed urls to dmenu')
source=('arg.h' 'config.def.h' 'config.mk' 'Makefile' 'st.1' 'st.c' 'st-find-urls' 'st.h' 'st.info' 'win.h' 'x.c' 'LICENSE')
md5sums=('SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP' 'SKIP')

provides=("${_pkgname}")
conflicts=("${_pkgname}")

pkgver() {
    printf "%s.r%s.%s" "$(awk '/^VERSION =/ {print $3}' config.mk)" \
        "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

# prepare() {
#     # skip terminfo which conflicts with ncurses
#     sed -i '/tic /d' Makefile
# }

build() {
    make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
    make PREFIX=/usr DESTDIR="${pkgdir}" install
    install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
