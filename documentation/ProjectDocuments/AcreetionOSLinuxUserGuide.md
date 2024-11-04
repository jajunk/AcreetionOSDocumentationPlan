# AcreetionOS Linux User Guide

***Export to website***


## Table of Contents

1. Introduction
2. System Requirements
3. Installation
4. Getting Started
5. Desktop Environment
6. System Configuration
7. Software Management
8. Networking
9. Troubleshooting
10. Support and Community

## 1. Introduction

Welcome to AcreetionOS Linux! This guide will help you get started with your new operating system and provide information on its key features and usage.

## 2. System Requirements

- CPU: 64-bit x86 processor (x86_64)
- RAM: Minimum 2GB, 4GB recommended
- Storage: At least 20GB of free space
- Graphics: Any modern graphics card with 3D acceleration
- Internet connection for updates and additional software

## 3. Installation

1. Download the Accretion Linux ISO from our official website.
2. Create a bootable USB drive using tools like Etcher or Rufus.
3. Boot your computer from the USB drive.
4. Follow the on-screen instructions in our graphical installer.
5. Choose your language, timezone, and keyboard layout.
6. Partition your disk as needed (the installer offers guided options).
7. Create your user account and password.
8. Wait for the installation to complete and reboot.

## 4. Getting Started

After installation, you'll be greeted by the login screen. Enter your username and password to access your desktop.

## 5. Desktop Environment

Accretion Linux uses a customized version of XFCE as its default desktop environment.

- The top panel contains the application menu, quick launch icons, and system tray.
- The desktop allows you to organize files and create shortcuts.
- Right-click on the desktop or panel for customization options.

## 6. System Configuration

- System Settings: Access from the application menu or by right-clicking the desktop.
- Key areas include:
  - Appearance: Customize themes, icons, and fonts
  - Display: Adjust resolution and multi-monitor setup
  - Power Management: Configure energy saving options
  - User Accounts: Manage users and groups

## 7. Software Management

AcreetionOS uses Pacman as its package manager in the CLI. For GUI interaction, AcreetionOS uses Pamac.

- Open Pamac from the application menu to browse and install software.
- Use the terminal for advanced package management:
  - Install a package: `sudo pacman -Sy package_name`
  - Remove a package: `sudo pacman -R package_name`
  - Update the system: `sudo pacman -Syyu`

## 8. Networking

- Click the network icon in the system tray to manage connections.
- For Wi-Fi, select your network and enter the password when prompted.
- For advanced network configuration, use the Network Manager tool in System Settings.
- In the case you are within a TTY, run ***'nmcli'*** for a TUI utility.

## 9. Troubleshooting

- If you encounter issues, check our FAQ at [acreetionos.org]("").
- For graphics issues, go the github found at [Github]("https://github.com/AcreetionOS") or [Gitea]("https://darrengames.ddns.net:30008/") and submit and issue.
## 10. Support and Community

- Official forums: [acreetionos.org/forum]("")
- Official Wiki: [wiki.acreetionos.org/]("") or the [Github Wiki Mirror.]("https://github.com/AcreetionOS/Wiki.git")
- IRC channel: [IRC]("")
- Discord Server: [Discord]("")
- Bug reports: [Github]("https://github.com/AcreetionOS/Wiki") or [Gitea]("https://darrengames.ddns.net:30008/")
- Wiki: https://wiki.acreetionos.org

Thank you for choosing AcreetionOS Linux. We hope you enjoy using our distribution!
