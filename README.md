# 🍷 Wine — Windows Compatibility Layer for Linux

**Wine** (Wine Is Not an Emulator) is a compatibility layer that enables you to run Windows applications on Linux, macOS, and BSD systems. It translates Windows API calls into POSIX calls, allowing many Windows programs to run smoothly without a virtual machine or dual boot.

---

## ✅ Features

* Runs many Windows applications and games natively on Linux
* Supports both 32-bit and 64-bit Windows apps
* No performance overhead of full virtualization or emulation
* Includes tools like `winecfg` for configuration and `winetricks` for installing libraries
* Compatible with lightweight window managers like i3, Openbox, and bspwm
* Allows creating isolated Wine prefixes (bottles) for different apps
* Supports DirectX, .NET frameworks (via wine-mono), and Internet Explorer components (via wine-gecko)

---

## 🔧 Installation

### Arch Linux

```bash
sudo pacman -S wine wine-mono wine-gecko winetricks
```

> **Note:** Enable multilib repo in `/etc/pacman.conf` to support 32-bit apps on 64-bit systems.

### Debian / Ubuntu

```bash
sudo apt install wine winetricks
```

### Fedora

```bash
sudo dnf install wine winetricks
```

---

## 🚀 Basic Usage

1. Configure Wine prefix (creates `~/.wine` by default):

```bash
winecfg
```

2. Run a Windows executable:

```bash
wine /path/to/application.exe
```

3. Use `winetricks` to install additional Windows components if needed:

```bash
winetricks
```

4. To run common Windows programs:

```bash
wine notepad.exe
wine calc.exe
```

---

## ⚙️ Configuration

Wine stores settings in the Wine prefix folder (`~/.wine` by default). You can configure:

| Tool         | Description                                                                      |
| ------------ | -------------------------------------------------------------------------------- |
| `winecfg`    | GUI for configuring drives, Windows versions, DLL overrides, graphics, and audio |
| `regedit`    | Edit the Windows registry inside Wine prefix                                     |
| `winetricks` | Script to install common Windows libraries and components                        |

---

## 🎯 Examples

### Run Notepad (built-in Windows app)

```bash
wine notepad.exe
```

### Install corefonts for better UI appearance

```bash
winetricks corefonts
```

### Create a new Wine prefix in a custom folder

```bash
WINEPREFIX=~/mywineprefix winecfg
```

### Run an installer inside a custom prefix

```bash
WINEPREFIX=~/mywineprefix wine ~/Downloads/setup.exe
```

---

## 📚 More Info

* Manual:

```bash
man wine
```

* Official website: [https://www.winehq.org/](https://www.winehq.org/)
* Arch Wiki: [https://wiki.archlinux.org/title/Wine](https://wiki.archlinux.org/title/Wine)

---

## 🧩 Alternatives

* `Proton` — Wine-based compatibility layer optimized for gaming (used in Steam)
* `PlayOnLinux` — GUI frontend to manage multiple Wine prefixes and Windows apps
* `Lutris` — Game manager that uses Wine and other runners for gaming on Linux
