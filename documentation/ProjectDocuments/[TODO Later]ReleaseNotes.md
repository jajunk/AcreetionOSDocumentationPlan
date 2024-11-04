# Accretion Linux 1.2.0 Release Notes

*DO RIGHT BEFORE RELEASE*

Release Date: July 15, 2024

## Table of Contents

1. Introduction
2. New Features
3. Improvements
4. Bug Fixes
5. Security Updates
6. Deprecated Features
7. Known Issues
8. Upgrade Instructions
9. Acknowledgments

## 1. Introduction

We are excited to announce the release of Accretion Linux 1.2.0. This version brings significant new features, performance improvements, and important bug fixes.

## 2. New Features

- **Full Disk Encryption**: The installer now offers an option for full disk encryption using LUKS.
- **Wayland Support**: Added support for Wayland display server alongside X11.
- **AccretionEdit**: Introduced a new default text editor with advanced features for both casual users and developers.
- **Custom Accretion Desktop Environment**: Switched from XFCE to our new custom-built Accretion DE for improved performance and user experience.

## 3. Improvements

- **Package Manager Performance**: Significantly improved AccretionPM's speed and efficiency, reducing update and install times by up to 40%.
- **Boot Time Optimization**: Reduced average boot time by 25% through init script optimizations.
- **Power Management**: Enhanced laptop battery life with improved power management settings.
- **Hardware Compatibility**: Expanded support for newer hardware, including the latest Intel and AMD processors.

## 4. Bug Fixes

- Fixed Wi-Fi disconnection issues on certain laptop models.
- Resolved memory leak in AccretionPM.
- Corrected graphics driver issues with specific NVIDIA cards.
- Fixed occasional freeze during system shutdown.
- Addressed file permission errors in home directory after user creation.

## 5. Security Updates

- Updated OpenSSL to address CVE-2024-0567.
- Implemented kernel page table isolation to mitigate Meltdown vulnerability.
- Enhanced default firewall rules for improved security.
- Updated all packages to their latest secure versions.

## 6. Deprecated Features

- Legacy system configuration tool (to be removed in 2.0).
- Support for 32-bit systems has been removed.

## 7. Known Issues

- Some touchscreen devices may have reduced functionality under Wayland.
- Certain proprietary applications may not work correctly with the new Accretion DE. We're working with vendors to address these issues.
- Hibernate function may fail on some laptop models. A workaround is documented in our wiki.

## 8. Upgrade Instructions

To upgrade from Accretion Linux 1.1.x:

1. Ensure your current system is up to date:
   ```
   sudo apm update && sudo apm upgrade
   ```
2. Run the release upgrade tool:
   ```
   sudo accretion-release-upgrade
   ```
3. Follow the on-screen instructions.

**Note**: Always back up your important data before performing a major upgrade.

## 9. Acknowledgments

We would like to thank our dedicated community of developers, testers, and users who have contributed to this release. Special thanks to:

- Jane Doe for implementing the new full disk encryption feature.
- John Smith for significant improvements to AccretionPM.
- The entire Accretion DE team for their tireless work on the new desktop environment.

We appreciate everyone who has filed bug reports, submitted patches, or helped other users on our forums.

For more detailed information about this release, please visit our changelog and documentation.

Thank you for using Accretion Linux!

