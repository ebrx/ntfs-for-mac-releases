# NTFS for Mac Community

[简体中文](README.md) | **English**

A free NTFS write utility for Mac, with a native SwiftUI interface in Chinese and English. No subscription, ads, or online activation.

## Video demo and contact

[![Watch the English NTFS for Mac demo on YouTube](images/ntfs-community-demo-cover-en.png)](https://youtu.be/IVS50FnyGXk)

**Watch the hands-on demo: [YouTube (English)](https://youtu.be/IVS50FnyGXk) · [Bilibili (Chinese)](https://www.bilibili.com/video/BV1Lmp36JEz7/)** · Creator: **Code It Real / 码上实现**

The video shows the app switching an NTFS drive from read-only to writable, then copying a test file, creating a folder, and renaming it. It uses the community preview available when it was recorded. For current downloads, supported configurations, and setup steps, follow this repository's documentation.

- **Free activation codes and contact:** Open the video, click the creator's avatar, and send **码上实现** a private message on Bilibili. Say that you would like to try NTFS for Mac Community. See the activation section below for details.
- **Bug reports:** Use Bilibili private messages or [GitHub Issues](https://github.com/ebrx/ntfs-for-mac-releases/issues). Include your chip, macOS version and build number, app version, and error text.
- **Software requests:** Leave a comment on the [YouTube demo](https://youtu.be/IVS50FnyGXk) or the Bilibili video describing the tool you want, the problem it should solve, and your use case. These requests help guide future tools.

**Code It Real — your wishlist for free software. You ask, I build.**

## Start here

**Check your system first: the current preview supports only Apple Silicon (M-series) Macs running macOS 26.6.2 (25G83).** Choose Apple menu → About This Mac, then click the system version to see the build number. If your configuration is outside this range, wait for a compatible release.

1. Download the all-in-one installer (PKG): [GitHub direct download](https://raw.githubusercontent.com/ebrx/ntfs-for-mac-releases/main/downloads/NTFS-for-Mac-Community-latest-All-in-One-arm64.pkg) · [Gitee direct download](https://gitee.com/ebrx/ntfs-for-mac-releases/raw/main/downloads/NTFS-for-Mac-Community-latest-All-in-One-arm64.pkg), then double-click the downloaded file. It includes the app, NTFS-3G engine, and macFUSE 5.4.0. **You do not need a separate driver download.** If the same macFUSE version is already installed, it skips reinstalling it.
2. Follow the [English installation guide](INSTALLATION.en.md) to allow the installer/app, enable both macFUSE file-system extensions, approve the community background service, and grant Full Disk Access. After granting permissions, quit the app normally and reopen it.
3. Send the creator a private message for a free activation code and activate it in the app. Select your NTFS drive, enable writing, and manage its files in Finder.

The all-in-one package installs the components, but you must still approve each required system setting. If the extension list does not show both macFUSE entries, follow the installation guide to register them for the current user with the official tool. If prompted to shut down and open Startup Security Utility, cancel and use the file-system extension settings instead. If the app mentions removable volumes but System Settings shows Full Disk Access, check that permission and quit/reopen the app normally.

**After initial setup and enabling automatic writing for a drive, reconnecting it while the app is running triggers a check and mount automatically.** Configure new drives separately. You can also enable “Open Finder after automatically enabling writing.” For devices without a volume UUID, the app remembers your choice using a verified NTFS serial number and capacity; changes to the drive letter, name, or interface do not change that identity. If it cannot read a valid persistent identity, writing must be enabled manually. Eject normally before disconnecting. The package combines installation into one entry point; first-time macOS security and permission approvals still require your action.

[English installation guide](INSTALLATION.en.md) · [English FAQ](FAQ.en.md) · [中文安装步骤](INSTALLATION.md) · [PKG checksum](downloads/SHA256SUMS) · [Current package version](downloads/latest.json)

Both direct download links point to `downloads/NTFS-for-Mac-Community-latest-All-in-One-arm64.pkg`. The URLs stay the same when the package is updated. The current package is **v0.2.5-preview.1** (16,970,865 bytes, about 16.18 MiB). Gitee mirror synchronization may be delayed, and Gitee requires login for this large file’s raw download (unauthenticated requests return HTTP 403). Use the GitHub direct link for a download without login. Check the [package metadata](downloads/latest.json) and [SHA-256 checksum](downloads/SHA256SUMS) for the version and file integrity.

The release page's `Source code` downloads contain this public repository's documentation; `third-party-source` contains dependency source code. **For installation, choose the All-in-One PKG linked above.**

**Automatic writing and Finder:** Version 0.2.5 adds a per-drive automatic Finder option and remembers automatic writing choices for NTFS USB drives without a UUID. It includes the button compatibility fix from 0.2.4. Devices are checked against the current connection identity and NTFS boot-sector serial number. Dirty and hibernated volumes are still rejected. Existing activation codes remain valid. If updating an older community version, first choose “Prepare for update or uninstall” in Settings, quit normally, and then install the new version.

**Recovering a failed installation:** Version 0.2.3 fixes the update-preparation flow when drivers are missing and retains checks/repairs for first-time installation and missing services. If an older installation is stuck with “NTFS dependencies are unavailable or their signature is invalid,” follow the [recovery instructions in the FAQ](FAQ.en.md) to reinstall the official dependencies before preparing the update. Downloading only the main app cannot repair an older service that is still running.

## Free activation codes

The app is in early testing and may still have stability or compatibility issues. Free activation codes help keep the initial testing group manageable. Requesting one by private message also gives you a way to reach the creator, report problems, and get updates. The codes are free, have no expiration, and are verified offline.

Codes are not tied to an Apple ID, account, or device. They can be shared; this is not strong copy-protection DRM. Future maintenance focuses on the community version. Although codes do not expire, system updates may require a new compatible app release, and indefinite maintenance is not promised.

## Current validation scope

The validated environment is Apple Silicon, macOS 26.6.2 / 25G83, and macFUSE 5.4.0. Tests passed for reading/writing a locally created NTFS image, recovery after restarting the helper service, true read-only mode, normal ejection, and activation checks. The all-in-one package's app bytes, signature, and original macFUSE components were checked for consistency. Local installer options were confirmed to skip the same installed macFUSE version.

**On October 10, 2026, the user confirmed successful installation on two Apple Silicon Macs, including an M3 Mac. Both were checked to run macOS 26.6.2 (25G83). The M3 Mac completed configuration and NTFS image read/write checks, and the user confirmed successful writing to a real drive.** Setup required manually registering the extensions and separately granting Full Disk Access. An 8 GB MBR USB drive without a UUID passed tests for Chinese directory names, renaming, Finder copying, SHA-256 readback after switching between read/write modes, refusal to write in true read-only mode, and normal ejection. Version 0.2.5 also passed automatic writing and automatic Finder opening after reconnecting a device without a UUID. The test directory was moved back to the Mac.

Independent extension registration on a clean Mac using only the all-in-one installer, every device/system combination, and complete metadata compatibility have not yet been validated. This remains a limited preview. Writing is refused when another OS build, an Intel Mac, or an incompatible dependency version falls outside the validated configuration.

The app is not notarized and does not have a Developer ID distribution signature. The outer PKG is unsigned; the app uses a free Apple Development certificate. macOS may block it on first launch; follow the [installation guide](INSTALLATION.en.md). Keep system protections enabled. This version does not require disabling SIP or lowering startup security.

## How it works

![Disk-writing architecture](images/disk-flow.en.svg)

The main app handles disk detection, mount management, automatic writing, and Finder access. NTFS-3G connects through macFUSE's FSKit backend. An authenticated helper verifies the caller, disk identity, engine, and permissions. The write engine runs as a normal user. Read-only mode uses Apple's NTFS implementation. Quitting or ejecting waits for writing to stop cleanly. Dirty and hibernated volumes are rejected. The app does not format, repair, force-write, or unlock BitLocker volumes.

![Offline activation architecture](images/activation-flow.en.svg)

The creator signs activation codes locally. The app stores only the public key. There is no online verification or cloud switch.

## Feedback and source code

Include your macOS version and build number, chip, app version, and error text in reports. Do not send passwords, activation codes, or private files from your drive. Download the latest installer using the GitHub / Gitee direct links above. Release notes and third-party source remain in this repository's Releases; you can also message the creator for information.

The main project's source remains private. This public repository contains installers, documentation, architecture diagrams, and required corresponding third-party source materials. See [THIRD-PARTY.md](THIRD-PARTY.md) and [FREEWARE-LICENSE.txt](FREEWARE-LICENSE.txt) for components and licenses.
