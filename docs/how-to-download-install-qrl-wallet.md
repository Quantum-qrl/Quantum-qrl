# How to Download and Install QRL Wallet, Step by Step

Installing a self-custodial wallet correctly matters more than installing most other software — get it wrong, and there's no support line that can recover funds from a mistake. This guide walks through installing [QRL Wallet](https://quantum-qrl.com/) the right way, on any of the platforms it supports.

## Before you start

QRL Wallet is available on Windows, macOS, and Linux as a desktop application, plus iOS and Android as mobile apps, and there's a browser-based web wallet as well. Whichever platform you're on, the process below covers the same core steps: get the software from the right place, verify it, install it, and secure your recovery phrase before you fund anything.

## Step 1: Go to the official download page

The single most important step in this whole process is also the easiest to get wrong. Search results for wallet downloads are routinely polluted with clones, phishing sites, and outright scams — the [official QRL Wallet download page](https://quantum-qrl.com/download) is the source to use, every time, not a link from a search ad or a forum post. Never install from a third-party mirror. The verified source repository, theQRL/qrl-wallet on GitHub, is a useful secondary reference for reading the code or checking release signatures, but it isn't where most users should go to grab the installer.

## Step 2: Choose your operating system

The download page offers dedicated, platform-specific builds: a `.exe` installer for Windows, a `.dmg` for macOS, and a `.zip` archive for Linux, plus store listings for the iOS and Android apps. Picking the wrong build for your OS is the most common self-inflicted install issue — double-check before you download.

## Step 3: Verify the download

This step is easy to skip and important not to. Every QRL Wallet release is signed with GPG by the QRL security team. Before you run the installer, compare the published checksum for your platform's build against the file you actually downloaded. Instructions for doing this, along with the public key you'll need, are published in QRL's official security documentation, linked from the [Security page](https://quantum-qrl.com/security). If the checksums don't match, stop — don't install, and re-download from the official page.

Verification matters more here than with typical consumer software because of what's at stake: a tampered installer is one of the more common ways wallet funds get stolen, and it's entirely preventable with a checksum comparison that takes under a minute.

## Step 4: Install and launch

Once verified, installation is standard for your platform — no unusual permissions requests, no confusing configuration screens. On first launch, the wallet generates your XMSS address locally, on your device. Nothing about this step transmits anything to a QRL Foundation server; the whole point of self-custody is that key generation happens entirely on hardware you control. If you want the underlying cryptographic detail on why this design choice matters, see [How XMSS Works](https://quantum-qrl.com/guides/how-xmss-works).

## Step 5: Back up your recovery phrase — before you fund anything

Write the recovery phrase down on paper (or another durable offline medium) and store it somewhere away from the device itself. This phrase is the only way to recover the wallet if the device is lost, stolen, or damaged. Complete this step before you deposit or buy any QRL — not after. There's no password reset and no support ticket that restores a lost recovery phrase; that's the tradeoff that comes with true self-custody, and it's covered honestly (not glossed over) on the [Security](https://quantum-qrl.com/security) page.

## A note specific to QRL's signature scheme

Because QRL uses XMSS rather than the elliptic-curve schemes most wallets use, there's one extra concept worth understanding before you start transacting heavily: one-time signature (OTS) keys. Each address has a finite number of them — 1,024 by default — and each one is designed to sign exactly once. This isn't something you need to worry about for casual use, but if you plan to make frequent transactions from the same address over a long period, it's worth reading [OTS Keys Explained](https://quantum-qrl.com/guides/ots-keys-explained) so you understand how key usage is tracked and what to do as you approach the limit.

## Using a Ledger hardware wallet

If you're pairing QRL Wallet with a Ledger device (Nano X or Nano S+), be aware that browser-based U2F connections can occasionally be less reliable than a direct desktop-app connection — using the desktop application generally provides a smoother Ledger experience than the web wallet. This is a known integration quirk worth planning around rather than troubleshooting mid-transaction.

## After installation: buying and using QRL

Once the wallet is installed, verified, and backed up, the next practical step for most people is funding it. QRL Wallet supports buying QRL directly with a bank card, delivered straight to an address you control with no separate exchange account or withdrawal step — the full walkthrough is in [How to Buy QRL Coin With a Bank Card](https://quantum-qrl.com/buy). For a broader orientation to what the wallet does and why it's built the way it is, the [homepage](https://quantum-qrl.com/) and [Quantum-Safe Wallet](https://quantum-qrl.com/quantum-safe-wallet) page are good starting points, and the [FAQ](https://quantum-qrl.com/faq) covers the questions that come up most often during setup.

If anything goes sideways during installation — a checksum mismatch, an installer that won't run, or a question about which build to pick — the [Contact page](https://quantum-qrl.com/contact) has the right channels for support and for reporting issues responsibly. The [full guides library](https://quantum-qrl.com/guides) has more walkthroughs beyond this one, and the [Privacy Policy](https://quantum-qrl.com/privacy) and [Terms of Use](https://quantum-qrl.com/terms) cover what data this site collects and the terms that apply to using self-custodial software.

---

### Related articles

- [Understanding One-Time Signature (OTS) Keys](understanding-ots-keys-qrl-wallet.md)
- [How to Buy QRL Coin With a Bank Card](how-to-buy-qrl-coin-bank-card.md)
- [QRL Wallet Security and Audit History, Explained](qrl-wallet-security-audits-explained.md)
- [QRL Wallet Review 2026](qrl-wallet-review-2026.md)
