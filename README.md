# SLPM — SoloLinux Package Manager

SLPM is the official package manager for **SoloLinux**, built as a secure wrapper around **pacman**.  
It preserves full Arch compatibility while adding identity protection, safety features, and a clean colourised interface.

---

## ✨ Features

- 🔒 Protects `/etc/os-release` from being overwritten by system packages  
- 🎨 Colourised CLI output  
- 🔄 Drop-in replacement for pacman (install, remove, upgrade, search, info)  
- 🛡 Identity enforcement after every package transaction  
- 📦 Uses pacman's package database (100% Arch compatible)  
- 🧰 Extra commands: backup, restore, config view  

---

## 📥 Installation

```bash
sudo cp slpm /usr/local/bin/slpm
sudo chmod +x /usr/local/bin/slpm
sudo slpm init
```

## 📘 Usage
### Install a package
`sudo slpm install <package>`

### Remove a package
`sudo slpm remove <package>`

### System upgrade
`sudo slpm upgrade`
### Search for a package
`slpm search <query>`
### Package info
`slpm info <package>`
### List explicitly installed packages
`slpm list`
### Backup protected files
`sudo slpm backup /etc/os-release`

### Restore protected files
`sudo slpm restore /etc/os-release`

### Toggle identity protection
`sudo slpm protect on`
`sudo slpm protect off`

### View SLPM config
`slpm config`
### 🛡 SoloLinux Identity Protection
SLPM guarantees that /etc/os-release always contains the correct SoloLinux identity.

It automatically restores the following enforced content:

```NAME="SoloLinux"
PRETTY_NAME="SoloLinux"
ID=sololinux
ID_LIKE=arch
BUILD_ID=rolling
ANSI_COLOR="0;38;2;37;104;151"
HOME_URL="https://archlinux.org/"
DOCUMENTATION_URL="https://wiki.archlinux.org/"
SUPPORT_URL="https://bbs.archlinux.org/"
BUG_REPORT_URL="https://gitlab.archlinux.org/groups/archlinux/-/issues"
PRIVACY_POLICY_URL="https://terms.archlinux.org/docs/privacy-policy/"
LOGO=archlinux-logo
```

If any package (e.g., filesystem, systemd) attempts to modify this file, SLPM will:

1. Detect the change

2. Reinstate the SoloLinux identity

3. Log the enforcement

4. Display a colourised warning

This ensures branding integrity across all updates.

### 🧪 Examples
#### Installing a package
`sudo slpm install htop`

#### Searching for packages
`slpm search bluetooth`

#### Removing software
sudo slpm remove neofetch

#### Fully upgrading the system
sudo slpm upgrade

### 🚧 Project Status

SLPM is in active development as part of the SoloLinux distribution.

#### Planned enhancements:

1. Automatic /etc/os-release immutability mode

2. Improved logging system

3. Optional ASCII art SoloLinux header

4. slpm fix-os-release repair tool

5. Repo signing + metadata system

6. Community contributions, ideas, and PRs are welcome.

### 📄 License

This project is licensed under the MIT License.

# 🌐 SoloLinux

SLPM is the official package manager for the SoloLinux operating system.


---
