# Install in order: one package, then first-run approvals

Release: **v0.2.3-preview.1**. No Terminal commands are needed. macOS security and permission approvals must still be completed by the user.

1. **Check compatibility.** Apple menu → About This Mac: Apple Silicon (M-series), **macOS 26.6.2 / build 25G83**. Click the version to see its build. Other builds and Intel Macs are not currently validated; activation does not bypass compatibility checks.
2. **Download [the All-in-One PKG](https://github.com/ebrx/ntfs-for-mac-releases/releases/download/v0.2.3-preview.1/NTFS-for-Mac-Community-0.2.3-preview.1-All-in-One-arm64.pkg)**, not `Source code` or `third-party-source`. Double-click and follow Continue → Agree → Install. Enter your Mac administrator password only in the system dialog. The package includes the app, NTFS-3G and official macFUSE 5.4.0 components. Matching macFUSE is retained. The app installs to `/Applications/NTFS for Mac Community.app`; do not additionally copy an old ZIP app.
3. **If macOS blocks the file**, confirm the source and optional SHA256SUMS, try opening once, then System Settings → Privacy & Security → Open Anyway for this specific file. The app may require a separate first-open confirmation. This preview has no notarization, Developer ID distribution signature or outer installer signature. Open Anyway is your permission, not an Apple security endorsement. If no allow option is offered, report the message and retain system protections. Version 0.2.2 adds an Open Privacy & Security button in the setup hint, plus shortcuts in the installer welcome/completion pages. Scroll to the security section and confirm the specific blocked file yourself. If the whole PKG or app is not allowed to run yet, its internal buttons cannot appear; the first approval still uses the manual Settings path. [Apple instructions](https://support.apple.com/102445).
4. **Enable both extensions.** System Settings → General → Login Items & Extensions → File System Extensions: enable **macFUSE** and **macFUSE (local)**. Follow system authentication/restart prompts. This FSKit backend does not require reduced startup security or disabling SIP.
5. **Open the app from Applications** and choose Enable Disk Access. Approve the Community background helper under Login Items & Extensions when requested, then return and refresh. Only if access is denied, follow the app guidance for Files & Folders removable/network volume access; if still required, grant Full Disk Access to the installed Community app, quit normally and reopen. Never send passwords to the author.
6. **Activate for free.** Message the author for a code, choose Free Activation, paste the complete code and confirm. No Apple ID, device identifier or network connection is needed. Save your code for reinstalls and compatible future versions using the same public key.
7. **Connect your NTFS disk**, select its volume, enable writing and wait for writable status, then Open in Finder. Use a new test directory to check copying/renaming. After opting that disk into automatic writing, future connections are checked and mounted while the app runs. New disks require a separate choice. Login at startup is optional. Eject normally before unplugging.

Activation is free, permanent and offline. Its only purpose is to limit early testing of potentially unstable software and provide a known contact for problems and updates. It has no other purpose.

## Completion and troubleshooting

Activation success alone does not establish readiness: the helper and filesystem backend must be ready, and the selected disk must show writable. Switching access remounts the disk and can take a moment. Unclean or hibernated volumes are refused: connect normally on Windows, close files and safely eject before retrying. This app does not force writing or repair disks. See [FAQ](FAQ.en.md).

## Updates and removal

**Do not delete/uninstall the app before an update.** Open old Community, press ⌘, for Settings and choose Prepare for Update or Removal, wait for writing to stop and the helper to unregister, then quit normally. Run the new All-in-One PKG or remove the app. The installer refuses to overwrite a running or registered Community app. Updating retains activation and does not clean user disk files.

A newer/unsupported macFUSE is not automatically downgraded. Before upgrading an older macFUSE, normally eject all FUSE volumes and quit apps using them. Do not remove shared macFUSE merely to uninstall this app. The original activation-free local app remains separate; do not let both apps manage the same disk.

Other-user fresh-machine installation, Community physical-disk acceptance and the complete GUI paste-activation flow have not yet been validated. This is a small-scope preview; a permanent code does not promise compatibility with every future OS or indefinite maintenance.

If the old app cannot prepare because dependencies are unavailable or invalid, follow the [old-install recovery steps](FAQ.en.md#dependencies-unavailable-or-invalid-cannot-prepare-an-update) before updating. The new idle cleanup fix cannot replace an already-running old helper.
