# QRL Wallet Security and Audit History, Explained

Security claims in crypto are cheap to make and expensive to verify. [QRL Wallet](https://quantum-qrl.com/) takes the harder, slower route: publish the source, submit it to independent auditors, and disclose limitations rather than smoothing them over. This article walks through what actually backs the wallet's security posture, in the order a careful evaluator would check it.

## Start with the cryptography, not the marketing

The foundation of QRL Wallet's security model is XMSS, a hash-based signature scheme standardized in NIST SP 800-208 and IETF RFC 8391. Unlike the ECDSA signatures used by Bitcoin and most other chains, XMSS doesn't depend on elliptic-curve math that a large quantum computer could eventually break with Shor's algorithm. The mechanics of how that works — Merkle trees, one-time signature leaves, and why hash functions resist the specific quantum attack that threatens elliptic curves — are covered in depth in [How XMSS Works](https://quantum-qrl.com/guides/how-xmss-works). What matters for a security assessment specifically is that this isn't a bolt-on feature: it's been the signing algorithm for every QRL address since the 2018 genesis block.

## Self-custody, verified in the code

QRL Wallet generates private keys and the XMSS one-time-signature state entirely on the user's device. None of that ever leaves the device or touches a QRL Foundation server — there's no account system to compromise because there's no server-side custody to begin with. That claim is checkable, not just stated: the wallet's source is public, and signed releases are published on GitHub under theQRL/qrl-wallet, so the download page's builds can be verified against the published source rather than taken on faith. The [download page](https://quantum-qrl.com/download) covers checksums and platform-specific installers for Windows, macOS, Linux, iOS, and Android.

## Three audits, spanning eight years

Independent audits are the part of a security story that's easiest to fake with vague language and hardest to fake with specifics, so here are the specifics. QRL's cryptographic implementation has been reviewed three times by three different firms:

- **Red4Sec, 2018** — reviewed the implementation around mainnet launch.
- **x41 D-Sec, 2018** — a second, independent review the same year.
- **Halborn, March 2026** — the most recent audit, which found zero cryptographic vulnerabilities in the current post-quantum library.

Three audits across eight years, from three unrelated firms, is a meaningfully different signal than a single audit run once at launch and never repeated. It shows the codebase has been checked again as the implementation evolved, not just at a single point in time when the project was smaller and simpler. The full audit history, along with links to the underlying reports, is maintained on the [Security page](https://quantum-qrl.com/security).

## The tradeoff QRL discloses instead of hiding

A responsible security writeup has to cover the actual limitations, not just the strengths, so here's the one that matters most for day-to-day use. XMSS is a stateful signature scheme: each address is provisioned with a finite number of one-time signature keys — 1,024 by default — and each key is only safe to use once. If every key on an address is exhausted without transferring the remaining balance to a fresh address first, the funds left behind become permanently unspendable. This isn't a bug; it's the direct, unavoidable consequence of the cryptographic design that makes XMSS quantum-resistant in the first place. QRL Wallet addresses it with visible key-usage tracking in the interface, and the practical mechanics — what an OTS index is, how to monitor it, and when to rotate to a new address — are covered fully in [OTS Keys Explained](https://quantum-qrl.com/guides/ots-keys-explained).

The other disclosed limitation is at the network layer, not the wallet layer: QRL's peer-to-peer node-identity cryptography currently still uses classical (non-post-quantum) methods. This doesn't affect fund custody, transaction signing, or consensus — all of which are already quantum-resistant — but it's worth knowing, and ML-KEM integration for that layer is in active development as of 2026.

## How this compares to the rest of the market

Most "quantum-safe" wallet marketing describes a future migration, not a shipped implementation. When you put QRL Wallet's XMSS-since-genesis history next to that pattern, the difference is less about superlatives and more about verifiable dates: 2018 mainnet launch, three audits since, and a signature scheme that was never patched in after the fact. The [Quantum-Safe Wallet](https://quantum-qrl.com/quantum-safe-wallet) page goes deeper into what separates a genuinely post-quantum implementation from a roadmap slide, and [QRL vs Bitcoin](https://quantum-qrl.com/qrl-vs-bitcoin) puts the comparison against the largest incumbent chain side by side.

If you're weighing QRL Wallet against other wallet categories entirely — hardware wallets, other software wallets, exchange custody — the [Safest Crypto Wallets 2026](https://quantum-qrl.com/safest-crypto-wallets-2026) guide covers what actually constitutes wallet security across the board, and the independent [QRL Wallet Review 2026](https://quantum-qrl.com/guides/qrl-wallet-review-2026) rates the tradeoffs plainly, strengths and constraints both.

## Getting started with a security-first mindset

If the audit history and cryptographic design check out for your needs, the practical next steps are: download from the [official download page](https://quantum-qrl.com/download), verify the release signature before installing, and back up your recovery phrase offline before funding the wallet. The step-by-step version of that process, including checksum verification, is in [How to Install QRL Wallet](https://quantum-qrl.com/guides/qrl-wallet-download-guide). Common security questions — including "is QRL Wallet safe to download" and "what are the disadvantages of QRL" — are answered directly in the [FAQ](https://quantum-qrl.com/faq).

---

### Related articles

- [How XMSS Hash-Based Signatures Actually Work](how-xmss-works-explained.md)
- [Understanding One-Time Signature (OTS) Keys](understanding-ots-keys-qrl-wallet.md)
- [The Safest Crypto Wallets in 2026: What Actually Counts](safest-crypto-wallets-2026-guide.md)
- [QRL Wallet Review 2026](qrl-wallet-review-2026.md)
