# Free activation and feedback

For **0.3.0**. Activation is free, perpetual and verified offline. There is no subscription, advertising or online activation.

## Where to request a code

Open the [Bilibili demonstration](https://www.bilibili.com/video/BV1Lmp36JEz7/), visit creator **码上实现 / Code It Real** through the author avatar and send a **Bilibili private message**. GitHub Issues are for public feedback; do not publish your machine code or activation code there.

## What to send

| Item | Where to find it | Needed? |
| --- | --- | --- |
| Application machine code `NTFSM-…` | App → Free Activation → Copy Machine Code | Required to sign a code for your Mac |
| App version | App → About; current release is 0.3.0 | Include it to identify the correct release |
| Chip model and macOS version/build | About This Mac; click the OS version for its build | Recommended for compatibility checks |

Suggested private message:

> I'd like to try NTFS for Mac Community 0.3.0. Machine code: [paste from app]. Chip: [model]. macOS: [version and build]. I will report the steps and errors if I encounter an issue.

No Apple ID, raw Mac serial number, account password, payment details or disk files are required. The machine code is an application-domain-separated hash of the hardware UUID. Nothing is uploaded automatically. The author uses the privately supplied machine code to issue activation and does not publish it.

## Activate

1. Paste the full **NTFSM2** code from the author's private reply into Free Activation and confirm.
2. Complete the separate filesystem extension, background helper and Full Disk Access approvals in the [installation guide](INSTALLATION.en.md). Activation grants no OS permission.
3. Wait for the automatic disposable-image self-test. After it passes, start with a disk containing no important data. Report the complete error if it fails.

The same code survives ordinary reinstalls and updates on that Mac. A different Mac or major hardware identity change requires free reissue. Legacy NTFSM1 codes do not activate 0.3.0; request a new machine-bound code for free. Perpetual activation does not promise support for all future systems. Offline activation has no remote revocation and is not claimed to be unbreakable.

## Why free activation is required

The software is still in early use and may have stability or compatibility issues. Codes keep the initial user group manageable and establish a contact for feedback and updated builds. There is no other purpose.

## What to include in feedback

- App version, chip model and macOS version/build.
- Drive type/capacity and the displayed filesystem, such as NTFS or TUXERA_NTFS. No disk serial number is needed publicly.
- The failing step, exact actions, full error text and whether it repeats.
- Optional redacted screenshots; for installation failures, the relevant Installer log excerpt.

Message the author privately or use [GitHub Issues](https://github.com/ebrx/ntfs-for-mac-releases/issues) with sensitive information removed. Never send passwords, private keys, activation codes or private disk contents. A TUXERA_NTFS mount is provided by another driver and does not validate this software's write path.

[Latest release](https://github.com/ebrx/ntfs-for-mac-releases/releases/latest) · [Installation](INSTALLATION.en.md) · [FAQ](FAQ.en.md) · [Tested scope](TESTED.en.md) · [中文](ACTIVATION.md)
