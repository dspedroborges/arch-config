# Arch Linux

This document outlines the steps taken to configure an Arch Linux system.

## Keyboard

- br-abnt2

## Profile

- Desktop environment: Lxqt
- Graphics driver: Intel (open-source)
- Greeter: sddm

## Applications

- Audio: pipewire
- Power management: power-profiles-daemon

# Firewall

```bash
sudo pacman -S ufw
```

```bash
sudo ufw status
```

```bash
sudo ufw enable
```

## Allows

```bash
sudo ufw allow ssh
sudo ufw allow http
sudo ufw allow https
```

# Tweaks

- Theme: https://www.gnome-look.org/p/1679919

### By range

```bash
sudo ufw allow 4000:4005/tcp
```

## Essential Development Tools

### Git

Install Git, the distributed version control system.

```bash
sudo pacman -S git
```

### Zig

Install Zig, a general-purpose programming language and toolchain.

```bash
sudo pacman -S zig
```

## Display Manager

### Ly

Ly is a lightweight TUI (Text User Interface) display manager, ideal for simple and fast logins at boot.

*   Ly is a TUI display manager
*   Good for simple, fast login at boot

For more information and installation instructions, visit the official GitHub repository:
[https://github.com/fairyglade/ly](https://github.com/fairyglade/ly)

## AUR Helper

### Yay

Install `yay`, an AUR (Arch User Repository) helper, to easily install packages from the AUR.

```bash
git clone https://aur.archlinux.org/yay-bin.git
cd yay-bin
sudo pacman -S base-devel
makepkg -si
```

## Web Browser

### Brave Browser

Install Brave Browser, a privacy-focused web browser, using `yay`.

```bash
yay -S brave-bin
```

## Terminal Emulator

### Kitty

Kitty is a fast, feature-rich, GPU-based terminal emulator.

Install Kitty using the official installer script:

```bash
curl -L https://sw.kovidgoyal.net/kitty/installer.sh | sh /dev/stdin
```

After installation, change the default terminal emulator in your XFCE4 settings: `settings > default applications > utilities > terminal emulator`.

## Screenshot Tool

### Flameshot

Flameshot is a powerful yet simple-to-use screenshot software.

```bash
sudo pacman -S flameshot
flameshot gui
```

To bind Flameshot to a key (e.g., Print Screen), change the default shortcut in XFCE4 settings: `application > settings > keyboard > application shortcuts`.

## File Manager

### NNN

NNN (n³) is a fast, minimalist file browser.

```bash
sudo pacman -S nnn
```

## Text Editor

### Neovim

Install Neovim, a modern Vim-based text editor, along with `ripgrep` and `fd` for enhanced search capabilities.

```bash
sudo pacman -S neovim ripgrep fd
```

Clone the Kickstart Neovim configuration for a ready-to-use setup:

```bash
git clone https://github.com/nvim-lua/kickstart.nvim.git ~/.config/nvim
```

## Media Players

### VLC

Install VLC media player, a highly versatile multimedia player.

```bash
sudo pacman -S vlc
```

## Streaming and Recording

### OBS Studio

Install OBS Studio for video recording and live streaming.

```bash
sudo pacman -S obs-studio
```

## Universal Package Manager

### Flatpak

Install Flatpak, a universal packaging system for Linux.

```bash
sudo pacman -S flatpak
sudo flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

## Programming Languages & Runtimes

### Node.js

Install Node.js and npm (Node Package Manager) for JavaScript development.

```bash
sudo pacman -S nodejs npm
```

### Go

Install Go (Golang) for Go language development.

```bash
sudo pacman -S go
```

## Databases

### PostgreSQL

Install PostgreSQL, a powerful, open-source relational database system.

```bash
sudo pacman -S postgresql
```

Initialize the PostgreSQL database and enable/start the service:

```bash
sudo -iu postgres initdb --locale $LANG -E UTF8 -D /var/lib/postgres/data
sudo systemctl enable --now postgresql
```

### SQLite

Install SQLite, a C-language library that implements a small, fast, self-contained, high-reliability, full-featured, SQL database engine.

```bash
sudo pacman -S sqlite
```

# Other

- VirtualBox