# Frequently asked questions

| Question | What to do |
| --- | --- |
| Which download should I install? | Choose `NTFS-for-Mac-Community-0.2.3-preview.1-All-in-One-arm64.pkg`. It contains the app and macFUSE 5.4.0. `Source code` contains public repository documentation; `third-party-source` is dependency source, not an installer. |
| Is installation completely automatic? | One package installs the components. You must still approve macOS security prompts, both filesystem extensions, the Community helper, and activate for free. Follow [the installation order](INSTALLATION.en.md). |
| Apple cannot verify the package? | This preview is unnotarized and its outer installer is unsigned. Confirm its source, try opening once, then Privacy & Security → Open Anyway for that file. The setup hint and installer pages now include Privacy & Security shortcuts. They are unavailable while the whole package/app is blocked from running; use the manual Settings path for the first approval. Keep Gatekeeper and SIP enabled. [Apple instructions](https://support.apple.com/102445). |
| “NTFS driver not bundled,” or no macFUSE extensions? | The 0.2.0 app-only package omitted the macFUSE system installer and had misleading legacy research-driver text. Prepare the old app for update and quit, install 0.2.3 All-in-One, then enable both macFUSE and macFUSE (local) extensions. Report the installer result if they remain absent. |
| Activated but still read-only? | Verify Apple Silicon / macOS 26.6.2 (25G83), macFUSE 5.4.0, both extensions enabled, helper approved and disk permissions allowed. Select your disk and explicitly enable writing. Activation does not grant OS permissions or override safety checks. Report the full status text. |
| “unclean file system”? | Normally connect on Windows, close files and safely eject, then retry on Mac. Do not bypass journal/hibernation checks; the app does not force writes or repair disks. |
| “Permission denied” or /dev/fd/0 errors? | Check the current All-in-One version, extension/helper approvals and permission guidance, then quit normally and reopen. Do not chmod device nodes or drivers. Report the full error if it persists. |
| “The volume identity has changed”? | Reconnection invalidated the old device identity, so old requests were stopped. Wait for scanning and reselect the current volume. Avoid repeated unplugging during operations. Report persistent failures; do not forcibly kill writers. |
| Disk missing from Finder? | Wait for remounting, use Open in Finder, and check Finder Settings → Sidebar → External disks. Reopen the Finder window if necessary. Report the app state if still missing; do not unplug during an operation. |
| All-in-One fails at the summary? | A first-install check in 0.2.1 and 0.2.2-preview.1 misread PlistBuddy’s missing-file diagnostic as a macFUSE version. Use **0.2.3-preview.1**, which includes that fix. Do not delete drivers or reduce security. Truly newer/unsupported versions still remain protected from downgrade. For other failures use ⌘L → Show All Logs and share the failure excerpt with the author. |
| macFUSE is already installed? | Matching 5.4.0 is skipped. Newer/unsupported versions are not downgraded. Normally eject all FUSE volumes and quit their apps before upgrading older versions. |
| Installer asks to quit or prepare for update? | 0.2.3 accepts inactive/not-found helper states and allows idle removal with unavailable dependencies. Prepare the old Community app for update in Settings, then quit with ⌘Q. If dependency errors prevent that, follow the recovery instructions below. Enabled or loaded services cannot be overwritten. |
| Is my Apple ID required? Does activation expire? | No developer account or author's Apple ID is required. Codes are free, permanent, offline and not account/device-bound. They only limit early testing and establish a contact for issues; there is no subscription, advertising or online activation. OS compatibility still requires a supported build. |

For feedback provide macOS version/build, M-series chip, app version, complete error and the step where it occurred. Do not send passwords, activation codes or private disk files. Other-user fresh-machine installation and complete Community physical-disk acceptance remain unvalidated.

[Installation](INSTALLATION.en.md) · [中文常见问题](FAQ.md)

## Dependencies unavailable or invalid; cannot prepare an update

Older helpers incorrectly require a working NTFS backend even when no writer exists. For an already-blocked old installation:

1. Eject FUSE volumes normally and quit other macFUSE applications. Do not interrupt a writer.
2. Install the [original signed macFUSE 5.4.0 recovery package](https://github.com/ebrx/ntfs-for-mac-releases/releases/download/v0.2.3-preview.1/macfuse-5.4.0.pkg). Do not downgrade a newer macFUSE version.
3. Open the old Community app → Settings (⌘,) → Prepare for update or removal; after success, quit with ⌘Q.
4. Install the [0.2.3-preview.1 All-in-One package](https://github.com/ebrx/ntfs-for-mac-releases/releases/download/v0.2.3-preview.1/NTFS-for-Mac-Community-0.2.3-preview.1-All-in-One-arm64.pkg).

If preparation still fails, share the complete error and Installer log privately. Invalid app assets/signatures can produce the same message and are not necessarily fixed by reinstalling macFUSE. Normal fresh installations use only the All-in-One package.
