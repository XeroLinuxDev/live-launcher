# Maintainer: XeroLinux <xerolinux@proton.me>

pkgname=xero-welcome
pkgver=0.1.2
pkgrel=1
pkgdesc="XeroLinux Live Welcome Application"
arch=('x86_64')
url="https://xerolinux.xyz"
license=('GPL-3.0-or-later')
depends=('gtk4' 'libadwaita' 'polkit')
makedepends=('cargo' 'rust')
source=()
sha256sums=()

build() {
    cd "$srcdir/.."
    cargo build --release
}

package() {
    cd "$srcdir/.."

    # Install binary
    install -Dm755 "target/release/xero-welcome" "$pkgdir/usr/bin/xero-welcome"

    # Install logo
    install -Dm644 "xero.png" "$pkgdir/usr/share/xero-welcome/xero.png"

    # Install icons
    install -dm755 "$pkgdir/usr/share/xero-welcome/icons"
    install -Dm644 assets/*.svg "$pkgdir/usr/share/xero-welcome/icons/"

    # Install autostart entry for live session
    install -Dm644 "xero-welcome.desktop" "$pkgdir/etc/xdg/autostart/xero-welcome.desktop"

    # Install icon for desktop entry
    install -Dm644 "xero.png" "$pkgdir/usr/share/pixmaps/xero-welcome.png"
}
