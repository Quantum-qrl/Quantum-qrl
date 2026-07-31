# QRL Wallet

**The official, self-custodial wallet for the Quantum Resistant Ledger — signing every transaction with XMSS since the 2018 genesis block, not a marketing claim added later.**

🔗 **Website:** [quantum-qrl.com](https://quantum-qrl.com)
📥 **Download:** [quantum-qrl.com/download](https://quantum-qrl.com/download)
🏛 **Maintained by:** the QRL Foundation (Zug, Switzerland) and Quantum Future Limited

---

## Why QRL Wallet

Most of the wallets people call "quantum-safe" today are elliptic-curve wallets with a roadmap slide promising a future upgrade. QRL Wallet isn't in that category. The Quantum Resistant Ledger launched its mainnet in 2018 as the first industrial implementation of **XMSS** (eXtended Merkle Signature Scheme) — a hash-based signature algorithm later standardized by NIST in SP 800-208. Every address on the chain, from the genesis block onward, has been signed this way. There is no migration to wait for.

That distinction matters because the threat XMSS defends against — Shor's algorithm running on a sufficiently large quantum computer — is specifically the kind of attack that breaks the ECDSA signatures used by Bitcoin, Ethereum, and the overwhelming majority of chains in production today. Read the full technical case on [Quantum-Safe Wallet](https://quantum-qrl.com/quantum-safe-wallet) and see the direct comparison on [QRL vs Bitcoin](https://quantum-qrl.com/qrl-vs-bitcoin).

QRL Wallet pairs that cryptography with straightforward self-custody: keys are generated on-device, never transmitted anywhere, and the user holds the only copy of the recovery phrase. See [QRL Wallet Security](https://quantum-qrl.com/security) for the full architecture, including the three independent audits (Red4Sec 2018, x41 D-Sec 2018, and Halborn in March 2026 — the most recent of which found zero cryptographic vulnerabilities).

## Features

- **XMSS hash-based signatures since genesis** — [quantum-safe-wallet](https://quantum-qrl.com/quantum-safe-wallet) · [how XMSS works](https://quantum-qrl.com/guides/how-xmss-works)
- **Self-custody, on-device key generation** — [security architecture](https://quantum-qrl.com/security)
- **Cross-platform** — Windows, macOS, Linux desktop; iOS and Android mobile; browser web wallet; Ledger hardware wallet support — [download](https://quantum-qrl.com/download)
- **In-wallet card purchases** — buy QRL with a bank card straight into an address you control, no exchange withdrawal step — [buy QRL](https://quantum-qrl.com/buy)
- **One-time signature (OTS) key management** — the honest tradeoff of a stateful signature scheme, explained plainly rather than buried — [OTS keys explained](https://quantum-qrl.com/guides/ots-keys-explained)
- **Three independent security audits, zero critical findings in the latest** — [security](https://quantum-qrl.com/security)
- **Open-source and publicly reviewable** — [source and signed releases on GitHub](https://github.com/theQRL/qrl-wallet)
- **QRL 2.0 / Project Zond on the roadmap** — an EVM-compatible, Proof-of-Stake successor network, in Testnet V2 as of Q1 2026 — [about the QRL Foundation](https://quantum-qrl.com/about)

## Guides & Resources

Everything on [quantum-qrl.com](https://quantum-qrl.com):

- [Home](https://quantum-qrl.com/) — wallet overview and download entry point
- [Download QRL Wallet](https://quantum-qrl.com/download) — official builds for every platform
- [Quantum-Safe Wallet](https://quantum-qrl.com/quantum-safe-wallet) — what actually makes a wallet quantum-resistant
- [Security](https://quantum-qrl.com/security) — XMSS architecture, audit history, honest disclosure of current limitations
- [QRL vs Bitcoin](https://quantum-qrl.com/qrl-vs-bitcoin) — direct cryptographic comparison
- [Buy QRL](https://quantum-qrl.com/buy) — step-by-step in-wallet card purchase guide
- [About the QRL Foundation](https://quantum-qrl.com/about) — project history, team, QRL 2.0 roadmap
- [FAQ](https://quantum-qrl.com/faq) — 28 questions across security, usage, buying, and comparisons
- [Guides](https://quantum-qrl.com/guides) — the full guide library
  - [How XMSS Works](https://quantum-qrl.com/guides/how-xmss-works)
  - [OTS Keys Explained](https://quantum-qrl.com/guides/ots-keys-explained)
  - [How to Install QRL Wallet](https://quantum-qrl.com/guides/qrl-wallet-download-guide)
  - [QRL Wallet Review 2026](https://quantum-qrl.com/guides/qrl-wallet-review-2026)
- [Quantum-Resistant Cryptocurrencies List](https://quantum-qrl.com/quantum-resistant-cryptocurrencies-list) — QRL compared against other post-quantum projects
- [QRL vs XRP](https://quantum-qrl.com/qrl-vs-xrp) — clearing up the ticker confusion, and the actual cryptography difference
- [Safest Crypto Wallets 2026](https://quantum-qrl.com/safest-crypto-wallets-2026) — what real wallet security means, beyond marketing
- [Contact](https://quantum-qrl.com/contact) — support, bug reports, responsible security disclosure
- [Privacy Policy](https://quantum-qrl.com/privacy)
- [Terms of Use](https://quantum-qrl.com/terms)

## Articles

In-depth, original write-ups on the cryptography, security model, and practical use of QRL Wallet:

1. [How XMSS Hash-Based Signatures Actually Work](docs/how-xmss-works-explained.md)
2. [QRL Wallet Security and Audit History, Explained](docs/qrl-wallet-security-audits-explained.md)
3. [How to Download and Install QRL Wallet, Step by Step](docs/how-to-download-install-qrl-wallet.md)
4. [Understanding One-Time Signature (OTS) Keys](docs/understanding-ots-keys-qrl-wallet.md)
5. [How to Buy QRL Coin With a Bank Card](docs/how-to-buy-qrl-coin-bank-card.md)
6. [QRL vs Bitcoin: The Quantum Security Difference](docs/qrl-vs-bitcoin-quantum-security.md)
7. [QRL vs XRP: Are They Related?](docs/qrl-vs-xrp-are-they-related.md)
8. [Quantum-Resistant Cryptocurrencies, Compared](docs/quantum-resistant-cryptocurrencies-compared.md)
9. [The Safest Crypto Wallets in 2026: What Actually Counts](docs/safest-crypto-wallets-2026-guide.md)
10. [QRL Wallet Review 2026](docs/qrl-wallet-review-2026.md)
11. [About the QRL Foundation: Origins and Roadmap](docs/about-qrl-foundation-history.md)
12. [QRL Wallet FAQ: The Most-Asked Questions, Answered](docs/qrl-wallet-faq-common-questions.md)

## About

QRL (Quantum Resistant Ledger) is a Layer-1 blockchain founded in 2016 by Dr. Peter Waterland, who identified that Bitcoin's and Ethereum's elliptic-curve signature schemes would eventually be vulnerable to quantum computers. The mainnet launched in 2018, making QRL the first production blockchain secured end-to-end by a hash-based, NIST-standardized signature scheme. The project is maintained today by the QRL Foundation, a Swiss non-profit based in Zug, alongside Quantum Future Limited. Full history and the QRL 2.0 (Project Zond) roadmap are on the [About page](https://quantum-qrl.com/about).

QRL Wallet is the Foundation's official self-custodial wallet software. It is open source, with signed releases on [GitHub](https://github.com/theQRL/qrl-wallet), and the official properties are **quantum-qrl.com** and **theqrl.org** — other sites using "QRL wallet" as a product name are unrelated to the QRL Foundation.

---

*Maintained by the QRL Foundation. For support, bug reports, or responsible security disclosure, see [quantum-qrl.com/contact](https://quantum-qrl.com/contact).*
