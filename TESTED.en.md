# Tested scope

Updated **2026-10-15**. Current stable release: **0.3.0**. [Machine-readable evidence](validation/0.3.0.json).

| Check | Actual result |
| --- | --- |
| Environment | Local Apple Silicon Mac, macOS 26.6.2 (25G83), macFUSE 5.4.0 |
| Installation/signature | All-in-One PKG upgrade passed; installed payload matched the signed build; matching macFUSE retained |
| Activation | Correct NTFSM2 machine-bound code accepted; signed code for another Mac and legacy NTFSM1 rejected; independent helper gate passed |
| Automatic image chain | All twelve checks passed; root backend status independently confirmed |
| Finder copy regression | Old failure reproduced in a disposable image; patched Foundation and same-directory Finder copies passed |
| Additional real-drive test | Final installed build duplicated the previously failing file on the 1 TB Drive with Command+C / Command+V; the duplicate persisted, original and duplicate hashes matched, and the user separately tested and confirmed the fix |
| UI/localization | Successful self-test banner hidden; 172 English/Chinese translation keys and format arguments verified |
| Code tests | 8 XCTest, 21 Swift Testing and 26 Python tests passed; 1 independently configured integration test skipped and the installed complete image chain separately exercised |

The twelve image checks cover ordinary-user read/write, same-volume copies of an empty-FinderInfo file into the same and a Unicode directory, root raw FD writing, wrong registry/NTFS-serial rejection, daemon restart recovery, same mount source, process identity, real read-only EROFS, unchanged read-only image hash, independent readback and normal eject. Only self-created disposable images are used.

## Historical scope

Older 0.2.x builds were installed on two Apple Silicon Macs running 26.6.2 (25G83), including an M3. A 1 TB drive and an 8 GB MBR USB drive without a UUID have records for writing, Unicode names, renaming, read-only rejection and normal eject. Version 0.2.5 passed UUID-less automatic writing and Finder reconnection. These are historical results, not a claim that 0.3.0 was re-tested on every one of those devices.

## Eligibility and remaining limits

Apple Silicon (including the M5 architecture) on macOS 26.4–27.x may attempt per-Mac self-test without an exact-build install whitelist. This is not proof of every chip/system/device combination. Full macOS 27 validation, a dedicated M5 Mac, clean-machine package-only extension registration, long-term multi-Mac stability and all metadata operations remain pending.

Actual OS build, code, policy and dependency changes invalidate the root-owned receipt and require retesting. Historical 25G83 evidence is unchanged. Signature, dependency hash, disk identity, dirty-volume and hibernation checks remain enforced. TUXERA_NTFS is another driver's mount and does not validate this app.

The app uses Apple Development signing. The outer PKG is unsigned and unnotarized; first use may require separate Open Anyway and OS permission approvals.

[Latest release](https://github.com/ebrx/ntfs-for-mac-releases/releases/latest) · [Installation](INSTALLATION.en.md) · [Activation/feedback](ACTIVATION.en.md) · [中文](TESTED.md)
