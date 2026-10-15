# Free activation: illustrated guide

For **NTFS for Mac Community 0.3.0**. Follow this order: **installation and OS approvals → request a bound code → activate → automatic self-test → expendable-drive test**.

[Latest release](https://github.com/ebrx/ntfs-for-mac-releases/releases/latest) · [Installation first](INSTALLATION.en.md) · [中文教程](ACTIVATION-GUIDE.md)

## Where to click

![The Settings activation button, Copy machine code, activation-code field and Activate for free button, numbered 1 to 4](images/activation/activation-steps-0.3.0.png)

*Prepared from actual 0.3.0 English-interface screenshots with privacy redaction and numbered annotations. The machine code and authorization ID are hidden. This example Mac was already activated, so it shows the green status; new users will not see Permanently activated before activation. Button positions/functions are the same in Chinese. Do not copy placeholder text from the image.*

| Marker | Button or field | Action |
| --- | --- | --- |
| ① | Free permanent activation | Open the activation sheet from Settings |
| ② | Copy machine code | Copy this Mac's machine code and privately send it to the author |
| ③ | Activation code field | Paste the complete activation code received from the author |
| ④ | Activate for free | Confirm activation, then wait for the automatic self-test |

## 1. Open Free permanent activation

Open **NTFS for Mac Community** from Applications. While it is the active app, press **⌘,** to open Settings. Click **① Free permanent activation**. You can also open Settings from the app menu in the menu bar.

Install the current version and separately approve both macFUSE filesystem extensions, the Community background helper and Full Disk Access using the [installation guide](INSTALLATION.en.md). An activation code grants none of those OS permissions.

## 2. Copy the machine code and request activation

Click **② Copy machine code**. It starts with **`NTFSM-`** and identifies this Mac for this app; it is not the raw Mac serial number.

Open the [Bilibili demonstration](https://www.bilibili.com/video/BV1Lmp36JEz7/), visit creator **码上实现 / Code It Real** through the author avatar and send a **Bilibili private message**:

> I'd like to try NTFS for Mac Community 0.3.0.
> Machine code: [paste the complete code copied from the app]
> Chip: [model, for example M3]
> macOS: [version and build]
> If I encounter an issue, I will send the actions and complete error.

**The app machine code and app version are required.** Chip model and macOS version/build are recommended for compatibility checks. No Apple ID, raw Mac serial, password, payment or disk file is needed. Do not post machine or activation codes in public comments or Issues.

## 3. Paste the code from the author's private reply

The author replies with a machine-bound activation code starting with **`NTFSM2.`**. Return to the activation sheet and paste the **complete activation code** into **③**.

| Item | Source | Destination |
| --- | --- | --- |
| `NTFSM-…` machine code | Copy machine code in the app | Private message to the author |
| `NTFSM2.…` activation code | The author's private reply | Activation code field in the app |

**Do not paste the machine code as the activation code.** Copy the full code without extra explanations, quotation marks or ellipses. The activation button is disabled while the field is empty. Example prefixes do not activate the app.

## 4. Activate and confirm the status

Click **④ Activate for free**. After success, open Settings again and confirm **Permanently activated**. The status in Settings and the green label in the activation sheet both confirm activation.

Activation is free, perpetual and verified offline, without an online account. The same code survives ordinary reinstalls and updates on that Mac. Another Mac or a major hardware identity change requires free reissue. Legacy NTFSM1 generic codes do not activate 0.3.0; request a new bound code for free.

## 5. Wait for self-test, then use an expendable drive

Return to the main window and wait for the automatic disposable NTFS image self-test. Physical writing remains disabled until it passes. The top self-test prompt disappears after success. On failure, read Details and send the complete error to the author; do not repeatedly force-quit or unplug drives.

Start with a **drive containing no important data**. Verify its name and capacity, enable writing, wait for read/write status and open it in Finder. Create a separate test folder, add a test file and try **⌘C / ⌘V**. Eject normally when finished. Do not use important data for a first test.

OS, app, helper or dependency updates require retesting. Apple Silicon / macOS 26.4–27.x is an eligibility range, not proof of every system or device. See [actual tested scope](TESTED.en.md).

## Troubleshooting

| Situation | What to do |
| --- | --- |
| Cannot find activation | Make sure this is **Community**. Use ⌘, → Free permanent activation, not Prepare for update or removal |
| Code invalid or belongs to another Mac | Check the complete code and the machine code used to request it; privately ask the author to verify the match. Do not publish the code |
| I have an old generic code | Send this Mac's machine code for free NTFSM2 reissue |
| Activated but read-only | Check both extensions, helper approval, Full Disk Access and current self-test. Activation cannot bypass dirty/hibernated-volume checks |
| TUXERA_NTFS is displayed | Another driver mounted that volume; its writing does not validate this app |
| I connected another drive | Activation is bound to the Mac, not a drive; configure automatic writing separately for a new disk |

Codes keep the early user group manageable and establish a feedback contact; they have no fee or other purpose. Report app version, chip, OS version/build, actions and full errors, with personal information removed. Never send passwords or private disk contents.

[Activation and feedback](ACTIVATION.en.md) · [Installation](INSTALLATION.en.md) · [FAQ](FAQ.en.md) · [Latest release](https://github.com/ebrx/ntfs-for-mac-releases/releases/latest)
