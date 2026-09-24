# 📦 Archive System Releases

Public distribution repository for **Archive System** Windows releases.

## Current release

**2.2.20** is the current application version configured in the source repository.

When a release is published, this repository contains:

- Windows installer: `Archive-System-Setup-<version>.exe`
- Update manifest: `latest.json`
- Release notes published with the GitHub Release

## Installation

1. Download the Windows installer from the **Releases** page.
2. Run the installer and complete the setup wizard.
3. On a fresh installation, sign in with:
   - Username: `manager`
   - Temporary password: `1234`
4. Change the temporary Manager password when prompted.

### Existing installations

Install the new version normally over the existing installation. The application is designed to preserve its persistent data, including the local database, attachments and settings.

**Do not manually delete `%APPDATA%\\ArchiveSystem` before installing an update.**

## Updates

Archive System checks this public repository for newer releases.

The release manifest `latest.json` contains the technical version, release notes, installer filename, file size and SHA-512 checksum.

Only a technically newer semantic version should be published. For example:

- `2.2.20` → `2.2.21` = newer release
- `2.2.20` → `2.2.20L` = not a newer technical application version

## Release history

See the GitHub **Releases** and **Tags** pages for published versions.

## Source code

The full source code is maintained separately in the private repository:

`MrN0oo0B/Archive-System`

## Support

- Email: mare_mar14@hotmail.com
- Phone / WhatsApp: +964 7702196422
