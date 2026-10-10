# Community test edition: installation and updates

Preview v0.2.0-preview.1 passed self-created NTFS image and activation-gate checks. The actual PKG/ZIP payloads and application signatures are verified. Installation on a different user’s Mac, community-edition physical disks and the complete paste-to-activate UI flow have not yet been accepted. This is a small-scope test release.

Target: Apple Silicon, macOS 26.6.2 / 25G83 and macFUSE 5.4.0. Other OS builds or dependency fingerprints refuse writing until a matching validated release is available.

1. Install the matching macFUSE version from https://macfuse.github.io/ and enable both macFUSE FSKit extensions in System Settings > General > Login Items & Extensions > File System Extensions. This route does not require lowering startup security or disabling SIP.
2. Verify the Release SHA256SUMS. Run the PKG to install `/Applications/NTFS for Mac Community.app`, or copy the app from the ZIP to that same location.
3. This free development-signed test edition is not notarized. macOS may block the first launch. After checking the source and checksum, try opening it and use the applicable Open Anyway confirmation in Privacy & Security. If no confirmation is available, report the error rather than disabling system protections. Apple guidance: https://support.apple.com/102445
4. Choose Enable disk access and approve the community background helper when prompted. Grant removable-volume access, or Full Disk Access when required, to this exact installed app and restart it. Enter passwords only in macOS dialogs.
5. Message the author for a free code and paste it in Free permanent activation. There is no account, device binding, online check or expiry. Save the code for reinstalls and compatible updates.
6. Enable writing for your own NTFS volume and opt it into automatic writing. The app must be running; new volumes require separate consent. Eject through the app before disconnecting the cable.

The existing local edition is activation-free and uses independent identifiers. Do not let both editions manage the same volume concurrently.

For updates/removal, choose Prepare for update or removal in Settings, wait until writes stop and the helper is unregistered, then quit before running the installer or removing the community app. The installer refuses to overwrite an active/registered edition. Codes and user disk files are retained.

Unclean/hibernated volumes are rejected. Safely close and eject them on Windows before retrying. The app does not format, repair or force-write disks. Permanent activation is not a guarantee of support for every future OS; updated compatibility releases may be necessary. Development signing certificates also have their own lifecycle, separate from activation codes.

## Why a free activation code is required

The software is in early testing and may still have stability or compatibility issues. Free activation codes are intended only to keep initial testing manageable and limit how many users an unexpected issue could affect. Requesting a code by direct message also gives you a way to contact the author, report problems and find updates. There is no other purpose. Codes are free, permanent and verified offline.
