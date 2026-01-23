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

## Firewall

```bash
sudo pacman -S ufw
```

```bash
sudo ufw status
```

```bash
sudo ufw enable
```

### Allows

```bash
sudo ufw allow ssh
sudo ufw allow http
sudo ufw allow https
```

### By range

```bash
sudo ufw allow 4000:4005/tcp 
```

## Tweaks

- Openbox Themes: https://www.box-look.org/browse?cat=140&ord=latest
- LXQt Themes: https://www.opendesktop.org/browse?cat=446

```bash
sudo mv path/to/theme /usr/share/themes/
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

## Trash Can

```bash
sudo pacman -S gvfs-bin gvfs-smb
```

## Display Manager

### Ly

Ly is a lightweight TUI (Text User Interface) display manager, ideal for simple and fast logins at boot.

* Ly is a TUI display manager
* Good for simple, fast login at boot

For more information and installation instructions, visit the official GitHub repository:
[https://github.com/fairyglade/ly](https://github.com/fairyglade/ly)

## Lock Screen

### xsecurelock

```bash
sudo pacman -S xsecurelock
```

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
sudo pacman -S kitty
```

```bash
kitty +kitten themes
```

```bash
vim ~/.config/kitty/kitty.conf
enable_audio_bell no
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

## Virtualization
- **VirtualBox** – Run other OSes in a virtual machine  
  - **Arch Linux:** `sudo pacman -S virtualbox`  
  - **AUR (for extension pack):** `yay -S virtualbox-ext-oracle`

## Bootable USB / OS Tools
- **Ventoy** – Boot multiple ISOs from one USB  
  - **Arch Linux:** `yay -S ventoy-bin`  
  - **Other OSes:** Download installer from [Ventoy website](https://www.ventoy.net/)

## Remote Access
- **AnyDesk** – Remote desktop access  
  - **Arch Linux:** `yay -S anydesk`  
  - **Other OSes:** Download installer from [AnyDesk website](https://anydesk.com/)

## Password Management
- **KeePassXC** – Password manager  
  - **Arch Linux:** `sudo pacman -S keepassxc`  

## Productivity & Office
- **LibreOffice** – Office suite  
  - **Arch Linux:** `sudo pacman -S libreoffice-fresh`  
- **MarkText** – Markdown editor  
  - **Arch Linux:** `yay -S marktext-bin`  
- **OpenBoard** – Interactive whiteboard  
  - **Arch Linux:** `yay -S openboard`

## Multimedia
- **Gimp** – Image editor  
  - **Arch Linux:** `sudo pacman -S gimp`  
- **Audacity** – Audio editor/recorder  
  - **Arch Linux:** `sudo pacman -S audacity`  
- **Quod Libet** – Music player  
  - **Arch Linux:** `sudo pacman -S quodlibet`  
- **Freetube** – YouTube without ads, option to download videos  
  - **Arch Linux:** `yay -S freetube-bin`

## Download & Torrent Tools
- **Qbittorrent** – Torrent client  
  - **Arch Linux:** `sudo pacman -S qbittorrent`  
- **yt-dlp** – Download videos/audio from web  
  - **Arch Linux:** `sudo pacman -S yt-dlp`  

## System Integration & Utilities
- **KDE Connect** – Phone-desktop integration  
  - **Arch Linux:** `sudo pacman -S kdeconnect`  
- **Timeshift** – System snapshots & restore  
  - **Arch Linux:** `sudo pacman -S timeshift`  
- **Espanso** – Text expansion  
  - **Arch Linux:** `yay -S espanso`

## System Monitoring
- **Btop / ytop / glances / htop** – System monitoring  
  - **Arch Linux:** `sudo pacman -S btop ytop glances htop`  
- **Fastfetch** – System info summary  
  - **Arch Linux:** `yay -S fastfetch-bin`  
- **lm-sensors** – CPU, GPU, motherboard temps, fan speeds  
  - **Arch Linux:** `sudo pacman -S lm_sensors` then `sudo sensors-detect`  
- **hddtemp** – Check hard drive temperature  
  - **Arch Linux:** `sudo pacman -S hddtemp`  
- **smartmontools (smartctl)** – Monitor HDD/SSD health  
  - **Arch Linux:** `sudo pacman -S smartmontools`

## Networking & Security
- **Wireshark / mitmproxy** – Network analysis & debugging  
  - **Arch Linux:** `sudo pacman -S wireshark-qt mitmproxy`  
- **nmap** – Scan networks  
  - **Arch Linux:** `sudo pacman -S nmap`

## Android on Linux
- **Waydroid** – Run Android apps on Linux  
  - **Arch Linux:** `yay -S waydroid-git`  

## Stress Testing & Diagnostics
- **stress-ng** – Stress test CPU, memory, disks  
  - **Arch Linux:** `sudo pacman -S stress-ng`  
- **memtest86+** – Check RAM for errors  
  - **Arch Linux:** `sudo pacman -S memtest86+` (boot from GRUB/USB)  
