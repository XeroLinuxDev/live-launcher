# XeroLinux Live Welcome

A beautiful welcome application for XeroLinux Live ISO, built with Rust and GTK4/Libadwaita.

![Screenshot](screenshot.webp)

## Features

- Modern, elegant UI with animated starfield background
- Glowing logo animation
- Quick access to the Calamares installer
- Community links (Website, Discord, YouTube, GitHub, Ko-fi)
- Automatically starts on live session boot

## Dependencies

- gtk4
- libadwaita
- polkit (for launching installer with elevated privileges)

## Building

```bash
# Debug build
cargo build

# Release build
cargo build --release
```

## Installation

### Using PKGBUILD (Arch Linux)

```bash
makepkg -si
```

### Manual Installation

```bash
# Build release binary
cargo build --release

# Install binary
sudo install -Dm755 target/release/xero-welcome /usr/bin/xero-welcome

# Install assets
sudo mkdir -p /usr/share/xero-welcome/icons
sudo cp xero.png /usr/share/xero-welcome/
sudo cp assets/*.svg /usr/share/xero-welcome/icons/

# Install desktop file
sudo install -Dm644 xero-welcome.desktop /usr/share/applications/xero-welcome.desktop

# Install icon
sudo install -Dm644 xero.png /usr/share/pixmaps/xero-welcome.png

# Enable autostart (optional)
sudo install -Dm644 xero-welcome.desktop /etc/xdg/autostart/xero-welcome.desktop
```

## Links

- [XeroLinux Website](https://xerolinux.xyz)
- [Discord](https://discord.xerolinux.xyz)
- [YouTube](https://youtube.com/@XeroLinux)
- [GitHub](https://github.com/xerolinuxdev)
- [Donate](https://ko-fi.com/XeroLinux)

## License

GPL-3.0
