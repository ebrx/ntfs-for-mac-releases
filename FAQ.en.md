# Frequently asked questions

| Question | What to do |
| --- | --- |
| Which download should I install? | Choose `NTFS-for-Mac-Community-0.3.0-All-in-One-arm64.pkg`. It contains the app and macFUSE 5.4.0. `Source code` contains public repository documentation; `third-party-source` is dependency source, not an installer. |
| Is installation completely automatic? | One package installs the components. You must still approve macOS security prompts, both filesystem extensions, the Community helper, and activate for free. Follow [the installation order](INSTALLATION.en.md). |
| Apple cannot verify the package? | This release is unnotarized and its outer installer is unsigned. Confirm its source, try opening once, then Privacy & Security → Open Anyway for that file. The setup hint and installer pages now include Privacy & Security shortcuts. They are unavailable while the whole package/app is blocked from running; use the manual Settings path for the first approval. Keep Gatekeeper and SIP enabled. [Apple instructions](https://support.apple.com/102445). |
| “NTFS driver not bundled,” or no macFUSE extensions? | The 0.2.0 app-only package omitted the macFUSE system installer and had misleading legacy research-driver text. Prepare the old app for update and quit, install the current 0.3.0 All-in-One, then enable both macFUSE and macFUSE (local) extensions. If absent, follow the per-user registration command in the installation guide, then reopen Settings and enable both items. |
| Activated but still read-only? | Verify Apple Silicon / macOS 26.4–27.x, a successful current-build automatic self-test, macFUSE 5.4.0, both extensions enabled, helper approved and Community Full Disk Access separately enabled; quit with ⌘Q and reopen after approval. Select your disk and explicitly enable writing. Activation does not grant OS permissions or override safety checks. Report the full status text. |
| “unclean file system”? | Normally connect on Windows, close files and safely eject, then retry on Mac. Do not bypass journal/hibernation checks; the app does not force writes or repair disks. |
| “Permission denied” or /dev/fd/0 errors? | Check the current All-in-One version, extension/helper approvals and permission guidance, then quit normally and reopen. Do not chmod device nodes or drivers. Report the full error if it persists. |
| “The volume identity has changed”? | Reconnection invalidated the old device identity, so old requests were stopped. Wait for scanning and reselect the current volume. Avoid repeated unplugging during operations. Report persistent failures; do not forcibly kill writers. |
| Disk missing from Finder? | Wait for remounting, use Open in Finder, and check Finder Settings → Sidebar → External disks. Reopen the Finder window if necessary. Report the app state if still missing; do not unplug during an operation. |
| A same-folder copy appears and then disappears? | Some files have an empty FinderInfo attribute that made the old engine trigger an attribute error and Finder undo the copy. Version 0.3.0 normalizes this read and adds same-volume copying of this fixture to the automatic image self-test. No source-file deletion, formatting or disk repair is required. If it persists after updating, report the file type, app version and error; keep the original and do not send private contents. |
| All-in-One fails at the summary? | A first-install check in 0.2.1 and 0.2.2-preview.1 misread PlistBuddy’s missing-file diagnostic as a macFUSE version. Use **0.3.0**, which includes that fix. Do not delete drivers or reduce security. Truly newer/unsupported versions still remain protected from downgrade. For other failures use ⌘L → Show All Logs and share the failure excerpt with the author. |
| macFUSE is already installed? | Matching 5.4.0 is skipped. Newer/unsupported versions are not downgraded. Normally eject all FUSE volumes and quit their apps before upgrading older versions. |
| Installer asks to quit or prepare for update? | 0.2.3 accepts inactive/not-found helper states and allows idle removal with unavailable dependencies. Prepare the old Community app for update in Settings, then quit with ⌘Q. If dependency errors prevent that, follow the recovery instructions below. Enabled or loaded services cannot be overwritten. |
| Is my Apple ID required? Does activation expire? | No developer account or author's Apple ID is required. Codes are free, permanent, offline and bound to the application machine code, not an account. They only limit early testing and establish a contact for issues; there is no subscription, advertising or online activation. OS eligibility is a range; current-build self-test evidence is still mandatory. |

For feedback provide macOS version/build, M-series chip, app version, complete error and the step where it occurred. Do not send passwords, activation codes or private disk files. The user confirmed installation on two Macs, including a second M3 Mac. Both systems were checked as 26.6.2 (25G83); the second Mac passed image checks and the user confirmed physical-disk writing. Package-only registration on a clean machine and all device models and metadata operations remain unverified. The local 8 GB MBR USB drive passed Finder copying, Unicode directories and renaming, content verification after access-mode changes, true read-only rejection and normal eject. Its UUID-less automatic write and Finder reconnection workflow also passed in 0.2.5.

[Installation](INSTALLATION.en.md) · [中文常见问题](FAQ.md)

## Dependencies unavailable or invalid; cannot prepare an update

Older helpers incorrectly require a working NTFS backend even when no writer exists. For an already-blocked old installation:

1. Eject FUSE volumes normally and quit other macFUSE applications. Do not interrupt a writer.
2. Download the [official macFUSE 5.4.0 disk image](https://github.com/macfuse/macfuse/releases/download/macfuse-5.4.0/macfuse-5.4.0.dmg); open the DMG and run its PKG installer. Do not downgrade a newer macFUSE version.
3. Open the old Community app → Settings (⌘,) → Prepare for update or removal; after success, quit with ⌘Q.
4. Install the [0.3.0 All-in-One package](https://github.com/ebrx/ntfs-for-mac-releases/releases/download/v0.3.0/NTFS-for-Mac-Community-0.3.0-All-in-One-arm64.pkg).

If preparation still fails, share the complete error and Installer log privately. Invalid app assets/signatures can produce the same message and are not necessarily fixed by reinstalling macFUSE. Normal fresh installations use only the All-in-One package.

## Why separate approvals after installation and activation?

Installer/app security approvals, both filesystem extensions, the Community background helper and Full Disk Access are separate. Activation grants no OS permission. Automatic writing is chosen per disk; login at startup is another optional choice. See the [setup checklist](INSTALLATION.en.md).

## Asked to shut down and use Startup Security Utility?

Cancel that kernel-backend flow. This app uses FSKit; enable both items under File System Extensions instead. No reduced startup security is required. See the [official backend explanation](https://github.com/macfuse/macfuse/wiki/Getting-Started#fskit-backend).

## Files & Folders shows Full Disk Access instead of removable volumes?

Go to Privacy & Security → Full Disk Access, enable the installed Community app, then quit normally with ⌘Q and reopen. If the switch is already on and reopening does not help, report the full error for helper-state diagnostics.

## A new NTFS USB drive is detected, but writing and eject buttons are disabled

Some NTFS devices, including the MBR USB drive encountered during testing, do not publish a volume UUID to macOS. Update to **0.3.0**; 0.3.0 requires a newly issued machine-bound NTFSM2 code. The app binds manual operations to the current IOMedia attachment. The helper additionally verifies capacity, raw device identity and the NTFS boot-sector serial. Reconnection invalidates stale operations. Manual writing and normal ejection are supported. In 0.2.5, a verified NTFS serial and capacity can persist per-disk consent without a UUID. An optional Finder window opens after successful automatic mounting. A missing/default serial remains manual-only; reusable disk numbers or labels never grant consent. Dirty and hibernated volumes remain protected.


## Can I use different external devices?

Ordinary external NTFS disks and USB drives are supported within the stated OS range; labels, ports and BSD disk numbers do not bind consent. A 1 TB Drive and an 8 GB MBR USB drive have been tested. Enable automatic writing separately for each new disk; optionally enable Finder opening after automatic writing. The app must be running. A reformatted disk with a new identity requires a new choice. Exact volume clones can share UUIDs/serials and cannot always be distinguished. BitLocker is unsupported; dirty/hibernated volumes remain read-only. Not every device model or metadata operation has been verified.

## Where do I get activation, and what has passed?

See [free activation and feedback](ACTIVATION.en.md) for the Bilibili private-message route and required machine code/app version. See [tested scope](TESTED.en.md) for the installed 0.3.0 twelve-check chain, real-drive Finder copy and user confirmation. Full macOS 27 and dedicated M5 validation remain pending. Old app installers have been withdrawn; history and corresponding sources remain archived. Use the [latest stable release](https://github.com/ebrx/ntfs-for-mac-releases/releases/latest).
