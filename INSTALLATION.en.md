# Installation and first-run setup

Release **v0.3.0**: Apple Silicon / **macOS 26.4–27.x** / macFUSE 5.4.0. Exact OS builds no longer restrict installation; automatic disposable-image self-test must pass on each Mac.

**The All-in-One package installs components. Each macOS approval is separate.** Installation or activation success does not mean every permission is enabled.

| Separate item | Where | Purpose |
| --- | --- | --- |
| Installer security approval | Privacy & Security → Open Anyway for that file, if blocked | Allows only this installer |
| App security approval | First app launch; allow that app separately if blocked | Installer approval does not cover the app |
| macFUSE filesystem extension | General → Login Items & Extensions → File System Extensions | Enable **macFUSE** |
| macFUSE (local) filesystem extension | Same page | Also enable **macFUSE (local)** |
| Community background helper | App → Enable Disk Access; then Allow in Background | Allow **NTFS for Mac Community** |
| Physical-disk access | Privacy & Security → Full Disk Access | Enable the installed **NTFS for Mac Community** app; quit and reopen |
| Free activation | App → Free Activation | Software authorization only; it grants no OS permission |

If macOS separately requests approval for a macFUSE background item, allow it too. It is distinct from the Community helper. Enter passwords/Touch ID only in system dialogs.

## 1. Install the All-in-One package

Download [NTFS-for-Mac-Community-0.3.0-All-in-One-arm64.pkg](https://github.com/ebrx/ntfs-for-mac-releases/releases/download/v0.3.0/NTFS-for-Mac-Community-0.3.0-All-in-One-arm64.pkg), double-click and follow Continue → Agree → Install. It includes the app, NTFS-3G and official macFUSE 5.4.0. Matching macFUSE is retained. The app installs to `/Applications/NTFS for Mac Community.app`; do not copy an old ZIP app. `Source code` and `third-party-source` are not installers.

If blocked, confirm the source, try opening once, then Privacy & Security → Open Anyway for that specific file. The app may need a separate first-open approval. Internal settings shortcuts cannot appear while the whole package/app is blocked. [Apple instructions](https://support.apple.com/102445).

The app uses Apple Development signing; the outer PKG is unsigned and unnotarized. Open Anyway is your approval, not an Apple security endorsement.

## 2. Register and enable both filesystem extensions

System Settings → General → Login Items & Extensions → File System Extensions: enable **macFUSE** and **macFUSE (local)** separately.

### If neither extension appears

On the second Mac tested, macFUSE 5.4.0 files and signatures were valid, but extensions were not registered for the login user. In Terminal, as the user who will use the app, run:

```bash
/Library/Filesystems/macfuse.fs/Contents/Resources/macfuse.app/Contents/MacOS/macfuse install --components file-system-extensions
```

This selects only the filesystem-extension component. [Official component-install documentation](https://macfuse.github.io/2026/04/09/macfuse-5.2.0.html). Close and reopen System Settings, then enable both items. Registration does not replace user approval. Skip this command if both items already appear. If the path is missing or the command fails, report the output rather than repeatedly reinstalling.

### Restart versus Recovery Mode

Continue if no restart is requested. If the correct filesystem-extension flow requests a normal restart, save work and eject external disks normally before restarting.

If asked to shut down, hold the power button, enter Startup Security Utility or select Reduced Security, cancel that flow. It belongs to the kernel backend; this app uses FSKit and does not require changing startup security in Recovery Mode. Return to **File System Extensions**. [Official backend explanation](https://github.com/macfuse/macfuse/wiki/Getting-Started#fskit-backend).

## 3. Approve the Community background helper

Open the app from Applications → Enable Disk Access. Allow **NTFS for Mac Community** under General → Login Items & Extensions → Allow in Background; return and refresh. This enables the helper, not the filesystem extensions or Full Disk Access.

## 4. Enable Full Disk Access separately

The confirmed physical-write setup is Privacy & Security → **Full Disk Access → NTFS for Mac Community: on**. If absent, use + to select the installed app in Applications.

If Files & Folders shows “Full Disk Access” instead of a removable-volume toggle, go to the Full Disk Access page and check this app's switch. If removable-volume access alone still results in denial, use the same Full Disk Access path.

After enabling, **quit normally with ⌘Q and reopen from Applications**, then retry writing. Closing the window is insufficient. If already enabled and reopening does not help, report the complete error so the helper state can be checked. Granting disk access to SSH, Terminal or unrelated apps is not part of this setup.

## 5. Get a bound code, activate and wait for self-test

[Follow the illustrated activation guide](ACTIVATION-GUIDE.en.md).

Copy your machine code from Free Activation, then open the [Bilibili video](https://www.bilibili.com/video/BV1Lmp36JEz7/) and privately message creator **码上实现 / Code It Real** through the author profile. Send the app machine code and app version; chip and macOS version/build are recommended. Paste the full NTFSM2 reply into Free Activation. See [activation and required information](ACTIVATION.en.md).

No Apple ID, raw Mac serial or payment is needed. Do not publish machine or activation codes. Legacy NTFSM1 requires free reissue. Same-Mac normal reinstalls/updates retain the code; a different Mac or major hardware identity change needs free reissue. Codes are free, perpetual and offline, to keep early use manageable and establish a feedback contact.

Wait for all twelve automatic disposable-image checks, including empty-FinderInfo same-volume copying, daemon restart recovery, true read-only rejection and independent readback. Physical writing remains disabled until a pass; the top prompt disappears after success. OS-build, code or dependency changes require retesting. Report a full error if it fails. Start with an expendable disk. TUXERA_NTFS belongs to another driver and does not validate this app.

## 6. Connect your disk and verify writing

Connect the NTFS disk → select the correct volume → Enable Writing → wait for writable status → Open in Finder. Create a test directory and copy a file.

Automatic writing is an optional choice for each disk; reconnecting the same disk is handled while the app runs. New disks require a separate choice. Enable “Open Finder after automatic writing” to open a window only after a successful mount; at most one automatic attempt occurs per attachment. UUID-less disks use a verified NTFS serial and capacity; missing/default serials remain manual-only. Login at startup is another optional setting and is not enabled by helper approval. Remounting can take a moment; eject normally before unplugging. Unclean/hibernated volumes must be safely ejected on Windows before retrying; this app does not format, repair or force writes.

## Updates and removal

Open old Community → Settings (⌘,) → Prepare for Update or Removal → wait for writing to stop and helper unregistration → quit with ⌘Q → install the new All-in-One PKG or remove the app. Do not delete a running app. Activation is retained; user disk files are not cleaned.

If the old app cannot prepare because dependencies are unavailable/invalid, follow [old-install recovery](FAQ.en.md#dependencies-unavailable-or-invalid-cannot-prepare-an-update) first. New packages cannot replace a still-active old service. Newer/unsupported macFUSE is not downgraded. Eject FUSE volumes and quit their apps before upgrading older macFUSE. The original activation-free local app remains separate; do not let both manage the same disk.

## Validation and feedback

Update on **2026-10-28**: the author confirmed successful operation after upgrading the local Mac to **macOS 27.2 (26B123)**. The installed app is still **0.3.0 (build 10)** and its executable matches the published build. This is post-upgrade user feedback; a twelve-check self-test export and itemized physical-disk test report have not been collected for this OS. It does not validate every macOS 27 build, chip or device.

The installed 0.3.0 build passed local macOS 26.6.2 (25G83) package upgrade, signature/payload verification, machine-bound activation, all twelve image checks and the previously failing real Drive same-directory Finder copy. The duplicate persisted, hashes matched and the user separately tested successfully. Historical M3/8 GB UUID-less USB results and remaining limits are documented in [tested scope](TESTED.en.md).

For feedback send app version, chip, OS version/build, disk filesystem/capacity, actions and complete error. No password, activation code or private file is needed. See the [contact and feedback checklist](ACTIVATION.en.md).

[Latest release](https://github.com/ebrx/ntfs-for-mac-releases/releases/latest) · [Activation](ACTIVATION.en.md) · [FAQ](FAQ.en.md) · [中文](INSTALLATION.md)
