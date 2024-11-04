# AcreetionOS Linux: Architecture Overview

## 1. Introduction
The AcreetionOS Linux project is an x86_64 as of 2024. It supports basic packages for the user environment stable, but it does not add bloat, but instead gives the user choice on what they would like to download for their own usecase.

## 2. System Architecture

AcreetionOS Linux follows a modular architecture, built on top of the Linux kernel. The system is composed of the following major components:

### User Applications
|Self-Created| Community Created|
| ---------- | ---------------- |
| CInstaller |Archinstall     |
|            |Mate Terminal |
|            |gedit|
|            |VS Code |
|            |Nano|
|            |VI|
|            |xviewer
|            |xreader
|            |xarchiver
|            |xplayer
|            |pix 



[Full package list]("https://darrengames.ddns.net:30008/cobra3282000/AcreetionOS/src/branch/main/packages.x86_64")


### Desktop Environment
***Cinnamon***, *Mate, XFCE*

### System Services 
*Lightdm* \
*timeshift* \
*Pamac Update Service*
    

### Package Manager
*Pacman, AUR, Flatpak* 

### Init System
*Systemd*

### Linux Kernel
*Zen-Kernel*

### Hardware
*x86_64*


### 2.1 Linux Kernel

At the core of AcreetionOS Linux, we are using the Zen Kernel, a kernel with a variety of extra patches for performance improvements. It is managed by The Zen Kernel team found at https://github.com/zen-kernel/zen-kernel. 

### 2.2 Init System

AcreetionOS Linux uses systemd as its init system and service manager, handling the boot process and managing system services.

### 2.3 System Services

These include essential daemons and background processes such as:
- NetworkManager for network configuration
- Pipewire for audio management
- Xorg for display server

### 2.5 Desktop Environment
AcreetionOS uses the Cinnamon Desktop Environment on its flagship edition. On the secondary editions AcreetionOS Mate and XFCE will use Mate and XFCE respectively.


## 3. Key Subsystems
Pacman - package management
Gnome-keyring - GPG Key management
OpenSSH - If the user wants to use SSH
Lightdm - Login Manager
Cinnamon - Desktop Environment



### 3.1 Boot Process

1. Systemd-boot
2. Linux kernel initialization
3. Display manager launch and user logs in
4. User session start
5. Startup Applications launch

### 3.2 File System Hierarchy

Follows the Filesystem Hierarchy Standard (FHS) with some custom directories:
- /usr/share/icons icons or ~/.icons for themeing
- /usr/share/themes or ~/.themes for themeing
- /usr/lib/Cinstall for the Acreetion Installer

The remainder of software comes from the secured AcreetionOS Repositories.

### 3.3 User Management

Utilizes systemd-logind for user session management and PAM for authentication.

### 3.4 Networking

NetworkManager handles network connections, with a custom GUI front-end for easy user configuration within the Cinnamon Desktop Environment. In the terminal the user can use NMCLI, a TUI for NetworkManager.

## 4. Security Architecture

- SELinux for mandatory access control
    We are using SELinux for the ability to do as we please. SELinux is more complicated than Apparmor is but allows for more control on how applications are isolated. It is also more specific by specifying files via an inode number instead of a path.   
- Regular security updates through the package manager, which are pulling from a self-hosted and secured repository. 
- Firewall management is done through firewalld, and if the user wants to configure their own firewall, they can use GUFW, which uses software such as IPTables,etc.


## 5. Customization and Extension
- Acreetion OS launches with it's own set of themes. The themes may borrowed from other developer, and all credits are given on their README's.
- Cinnamon comes with the ability to theme, as well as use plugins. Future custom plugins make occur.
- Hook scripts may be installed depending on what hardware the user uses. In the case of Nvidia, Intel ARC, for instance, the hook is used to intall the GPU Drivers using DKMS.

## 6. Build and Release Process for the ISO image.

- Automated build system within Gitea
- ISO creation using custom scripts based on archiso within Gitea
- Continuous Integration/Continuous Deployment (CI/CD) pipeline for testing and releasing within a containerized and isolated environment.

This architecture is designed to be modular and flexible, allowing for easy customization and extension as the project evolves.

## 7. Build and Release Process for Packages.
Issue Description

The AcreetionOS Linux Project uses build machines, virtual machines, Docker containers, and more to build packages and test packages. Those containers pull source code and build packages using makepkg [https://wiki.archlinux.org/title/Makepkg]. Each day the containers pull from the project maintainers repositories of the packages below: 

alsa-firmware
alsa-plugins
alsa-utils
amd-ucode
appstream
appstream-glib
appstream-qt
appstream-qt5
arch-install-scripts
archinstall
arch-audit
archiso
archivetools
archlinux-appstream-data
archlinux-contrib
archlinux-keyring
archlinux-wallpaper
b43-fwcutter
base
base-devel
bind
blueberry
bluefish
bluez
bluez-utils
brltty
cinnamon
cinnamon-control-center
cinnamon-desktop
cinnamon-menus
cinnamon-screensaver
cinnamon-session
cinnamon-settings-daemon
cinnamon-translations
cloud-init
coreutils
cpio
cryptsetup
#cuda
#cuda-tools
curl
dbus
dbus-docs
dbus-glib
dbxtool
dconf
dconf-editor
ddgr
ddrescue
device-mapper
dhclient
dhcpcd
dialog
diffutils
dmidecode
dmraid
dnsmasq
dosfstools
duf
e2fsprogs
exfatprogs
edk2-shell
efibootmgr
efitools
ethtool
exfatprogs
fakeroot
fatresize
ffmpeg
firefox
firewalld
freetype2
fsarchiver
fuse2
fuse3
gcc
gcc-libs
gedit
gedit-plugins
git
gnome-console
gnome-keyring
gnome-screenshot
gnome-shell
gnu-netcat
gpart
gpm
gptfdisk
grml-zsh-config
grub
grsync
gsfonts
gst-libav
gst-plugin-pipewire
gst-plugins-bad
gst-plugins-ugly
gtk3
gtk4
haveged
hdparm
hwdata
hwdetect
hyperv
img2pdf
inetutils
intel-compute-runtime
intel-gmmlib
intel-graphics-compiler
intel-graphics-compiler
intel-media-driver
intel-ucode
intel-undervolt
iptables-nft
irssi
iw
iwd
jfsutils
ldns
less
lftp
libadwaita
libadwaita-docs
libdvdcss
libfido2
libgsf
libopenraw
libsmbios
libusb-compat
libva-intel-driver
libva-mesa-driver
libva-utils
libva-vdpau-driver
libvirt
libvirt-glib
lightdm
linux-atm
linux-firmware
linux-firmware-marvell
linux-zen
linux-zen-docs
linux-zen-headers
livecd-sounds
llvm
logrotate
lsb-release
lsscsi
lvm2
lynx
lz4
man-db
man-pages
metacity
mc
mdadm
meld
memtest86+
memtest86+-efi start up service thing*
mesa
mesa-utils
mesa-vdpau
meson
mkinitcpio
mkinitcpio-archiso
mkinitcpio-nfs-utils
mlocate
modemmanager start up service thing*
mtools
nano
nano-syntax-highlighting
nemo-emblemsbuild
nemo-fileroller
nemo-pastebin
nemo-preview
nemo-python
nemo-qml-plugin-configuration
nemo-qml-plugin-notifications
nemo-seahorse
nemo-share
networkmanager
networkmanager-openconnect
networkmanager-openvpn
nbd
ndisc6
net-tools
netctl
nfs-utils
nftablesbuild
nilfs-utils
nmap
ntfs-3g
ntp
nvidia
nvidia-utils
nvme-cli
open-iscsi
open-vm-tools
openconnect
openh264
openpgp-card-tools
openimagedenoise
openssh
openssl
openvpn
os-prober
pacman-contrib
partclone start up service thing*
parted
partimage
partitionmanager
pavucontrol
pcsclite
pdfgrep
perl
persepolis
pipewire start up service thing*
pipewire-alsa
pipewire-audio
pipewire-docs
pipewire-ffado
pipewire-jack
pipewire-pulse
pipewire-roc
pipewire-session-manager
pipewire-v4l2
pipewire-x11-bell
pipewire-zeroconf
pkgfile
polkit-gnome
poppler-glib
power-profiles-daemon
ppp
pptpclient
psensor
python-capng
python-packaging
python-pyqt5
pv
qemu-guest-agent
rebuild-detector
reflector
reiserfsprogs
rp-pppoe
rsync
rnnoise
rtkit Automated build system using Jenkins
- ISO creation using custom scripts based on archiso
- Continuous Integration/Continuous Deployment (CI/CD) pipeline for testing and releasing
rxvt-unicode-terminfo
sdparm
sequoia-sq
sg3_utils
smartmontools
s-nail
sof-firmware
spice-vdagent
squashfs-tools
stress-ng
sudo
sysfsutils
syslinux
system-config-printer
systemd-resolvconf
systemd-sysvcompat
tcpdump
testdisk
texinfo
thermald
tldr
touchegg
tmux
tpm2-tools
tpm2-tss
unrar
unzip
usb_modeswitch
usbmuxd
usbutils
vi
vkd3d
virtualbox-guest-utils
vpnc
vulkan-intel
vulkan-mesa-layers
vulkan-radeon
vulkan-swrast
vulkan-virtio
warpinator
webrtc-audio-processing
which
wireless-regdb
wireless_tools
wireplumber
wpa_supplicant
wvdial
x265
x42-plugins
xdg-user-dirs
xdg-utils
xed
xf86-input-libinput
xf86-video-amdgpu
xf86-video-ati
xf86-video-intel
xf86-video-qxl
xf86-input-vmmouse
xf86-video-vmware
xfsprogs
xl2tpd
xorg-server
xorg-xdpyinfo
xorg-xinit
xorg-xinput
xorg-xkill
xorg-xrandr
xorg-xwayland
xz
zsh

If the package change is found, it's source code gets pulled, as well as it's readme and builds against PKGBUILDs we have built/found. Once package are built the packages are put through a testing process for each packager to build successfully with Makepkg, and then be ran through the Cinstall [the in house AcreetionOS installer] script with automated inputs to prove the package installs successfully. If the package installs, then the package is pushed over to a private repository for "Manual Checking"; this repository is known as the TESTING AcreetionOS Repository. If the package does not succeed, the server writes out a log entry, as well as copies the README of the specified project, into a private repository on the gitea instance, in a repository called "Errors"; afterward sending a ping to project maintainers dedicated devices letting them know of the failure. Afterward developers manually investigate the issue from look for a fix with manual intervention. When the package gets to "Manual Checking", this package is in the TESTING AcreetionOS Repository, of which testers are running these packages on their daily driver machines.

In the case of the TESTING AcreetionOS Repository, it is ran on a "True until proven False" system, which assumes that the package is safe and tested unless the maintainer intervenes, removing the said package. Once maintainers remove the package from the TESTING repository in the case of instability, an "Issue Report" template is sent to said maintainer, reminding them to look into the issue and take necessary action on the package as well as document the reason the package was removed from the temporary testing repository. When the package is removed, it is assumed that the package must be reinstated at some point before the next release period. If the package has not been reinstated within three days of the release cycle, a server sends a reminder for said package to be dealt with by said maintainer. Each release cycle is 14 days. In the case of the package reminder being ignored, the repository pulls the last stable version as a placeholder and sends a ping to the head maintainer's devices about said package. The head maintainers handle the packages by hand at this point if not dealt with accordingly. If the package is stable and not intervened with, it is ran through the CInstall script for a check to verify the package still installs. When the package installs it is pushed to the AcreetionOS main repository for users to use.

Steps to learn the AcreetionOS Package build process:

Find source code and clone all packages in list above.
Learn about PKGBUILD. Found here: [https://wiki.archlinux.org/title/PKGBUILD]
Find/Make PKGBUILD for all packages above.
Learn about Makepkg: Found here: [https://wiki.archlinux.org/title/Makepkg]
Build all packages in list above with Makepkg.
Learn about Arch Linux Repositories Found here:
[https://www.joram.io/blog/custom-arch-linux-package-repository/]
and
[https://www.arcolinuxiso.com/how-to-create-your-own-online-arch-linux-repository-on-github-and-use-it-on-any-arcolinux/]
Add package to testing repository.
Wait for maintainer to test package on system natively.
Maintainer tests package and remove invalid/unstable packages and server automatically pushes stable packages to repository.
Manual Intervention to the AcreetionOS package process.

Find source code for all packages in list above.
Find/Make PKGBUILD for all packages above.
Build all packages in list above with Makepkg.
Add package to testing repository.
Wait for maintainer to test package on system natively.
Maintainer tests package and remove invalid/unstable packages.
Server automatically pushes stable packages.

Semi-Automated Package Process.

Server looks at package name and searches Github and Gitlab for package name. It then finds the source code for each package from the list above and pulls said repositories into separate directories for each project.
The server then looks for a PKGBUILDs for said package within the Arch Linux reositories using pkgctl; more about pkgctl here: [https://wiki.archlinux.org/title/Arch_build_system]. In the case the package has no PKGBUILD within the primary Arch Linux repositories, it then pings a maintainer for manual intervention on their primary device. Maintainer then handles the package from here.
Once the server has got said PKGBUILDs, the server then builds all packages above; using Makepkg. More on Makepkg can be found here: [https://wiki.archlinux.org/title/Makepkg] If Makepkg does not build successfully, a notification is sent to a maintainer on their designated device who then intervenes and fixes said issue.
After PKGBUILD successfully builds using Makepkg, server then puts packages into the TESTING repository.
Maintainer then tests package on system natively.
Maintainer then removes invalid/unstable packages and handle accordingly.
Server then automatically pushes stable packages to user repository.
Expected Behavior
The build system, testing system, as well as private repositories, lead to an experience where the user has very few system-level instabilities because of the long testing process of packages.

Additional Information

Read on Arch Build System: https://wiki.archlinux.org/title/Arch_build_system
Read on PKGBUILD: https://wiki.archlinux.org/title/PKGBUILD
[Ex PKGBUILD: https://aur.archlinux.org/cgit/aur.git/tree/PKGBUILD?h=python-async_interrupt]
Read on Makepkg : https://wiki.archlinux.org/title/Makepkg
Read on Arch Repositories:
[https://www.joram.io/blog/custom-arch-linux-package-repository/]
and
[https://www.arcolinuxiso.com/how-to-create-your-own-online-arch-linux-repository-on-github-
and-use-it-on-any-arcolinux/]
Read on Pacman: https://wiki.archlinux.org/title/Pacman#:~:text=The%20goal%20of%20pacman%20is,lists%20with%20the%20master%20server.
Environment
Currently Based on AcreetionOS [which is currently Based on Arch Linux.]

Priority Level
High

Impact
This is crucial for the project to be successful.

Acceptance Criteria
The build system and repositories are fully in production for users to use with a team that fully understands said system and how each piece fits into the build system.

Suggested Assignees
@Sprungles @cobra3282000 @jajunk

