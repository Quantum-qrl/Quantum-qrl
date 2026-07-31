# QRL Wallet FAQ: The Most-Asked Questions, Answered

This article pulls together the questions that come up most often about [QRL Wallet](https://quantum-qrl.com/) and the Quantum Resistant Ledger, in one place, answered directly. For the complete 28-question reference covering every category, see the full [FAQ page](https://quantum-qrl.com/faq).

## About the project

**What does QRL mean?** QRL stands for Quantum Resistant Ledger, a Layer-1 blockchain built to resist attacks from both classical and quantum computers. It launched its mainnet in 2018 as the first industrial implementation of XMSS, a hash-based post-quantum signature scheme.

**Who created QRL?** Dr. Peter Waterland founded the project in 2016, having identified that Bitcoin's and Ethereum's cryptographic signature schemes would eventually be vulnerable to sufficiently large quantum computers. It's maintained today by the QRL Foundation, a Swiss non-profit, and Quantum Future Limited. Full history is on the [About page](https://quantum-qrl.com/about).

**Is QRL still active?** Yes. Beyond the current mainnet, QRL 2.0 (Project Zond) — an EVM-compatible, Proof-of-Stake upgrade — is in Testnet V2 as of Q1 2026 and undergoing independent security audits ahead of mainnet launch.

## Security and trust

**Is QRL really quantum resistant?** Yes. QRL uses XMSS, a hash-based signature scheme standardized in NIST SP 800-208, in place of the ECDSA cryptography used by Bitcoin and Ethereum, which is vulnerable to Shor's algorithm on a sufficiently powerful quantum computer. Full detail in [How XMSS Works](https://quantum-qrl.com/guides/how-xmss-works).

**How secure is QRL?** The implementation has been reviewed by three independent security firms: Red4Sec (2018), x41 D-Sec (2018), and Halborn (March 2026). The most recent audit found zero cryptographic vulnerabilities in the current post-quantum library — see the full history on the [Security page](https://quantum-qrl.com/security).

**Is QRL Wallet safe to download?** Yes, when installed from the [official download page](https://quantum-qrl.com/download) on quantum-qrl.com. GitHub (theQRL/qrl-wallet) is a secondary route for reading the source or verifying release signatures — always check the GPG signature against the QRL Foundation's published key before installing.

**What are the disadvantages of QRL?** The main tradeoff is XMSS's stateful nature: each address has a limited number of one-time signature (OTS) keys, and reusing one is cryptographically rejected. If all keys on an address are exhausted without transferring remaining funds first, those funds become permanently unspendable. See [OTS Keys Explained](https://quantum-qrl.com/guides/ots-keys-explained) for how to manage this safely — it's a non-issue for typical usage patterns.

**Is QRL's peer-to-peer network fully quantum-resistant?** Custody, transaction signing, and consensus are quantum-resistant today. The peer-to-peer networking layer (node identity) currently uses classical cryptography, though this isn't spend- or custody-critical; ML-KEM integration for that layer is in active development as of 2026.

## Comparisons

**Is QRL related to XRP or Ripple?** No. They're separate, unrelated blockchains that happen to share a similar-looking three-letter ticker. Full breakdown in [QRL vs XRP](https://quantum-qrl.com/qrl-vs-xrp).

**Can quantum computers break Bitcoin?** Not today — no quantum computer currently exists at the scale needed. But Bitcoin's ECDSA signatures are theoretically vulnerable to a sufficiently large one in the future, unlike QRL's XMSS signatures. Detailed comparison in [QRL vs Bitcoin](https://quantum-qrl.com/qrl-vs-bitcoin).

**Are there other quantum-resistant cryptocurrencies?** Yes — IOTA (Winternitz one-time signatures), Algorand (Falcon-based signatures on state proofs), and QANplatform (a post-quantum smart contract layer) all have some post-quantum work in progress. Coverage and maturity vary significantly; see [Quantum-Resistant Cryptocurrencies, Compared](https://quantum-qrl.com/quantum-resistant-cryptocurrencies-list) for the full survey.

## Buying and using the wallet

**How do I buy QRL?** Directly inside QRL Wallet with a bank card — funds are delivered straight to an address you control, with no separate exchange account or withdrawal step. Full walkthrough in [How to Buy QRL Coin](https://quantum-qrl.com/buy).

**What platforms does QRL Wallet support?** Windows, macOS, and Linux desktop; iOS and Android mobile; a browser-based web wallet; and Ledger hardware wallet support (Nano X, Nano S+). Get started at the [download page](https://quantum-qrl.com/download), and the full setup process is in [How to Install QRL Wallet](https://quantum-qrl.com/guides/qrl-wallet-download-guide).

**Does QRL Wallet ever see my private keys?** No. Keys and XMSS signing state are generated and stored entirely on-device and are never transmitted to any server — genuine self-custody, detailed in [QRL Wallet Security](https://quantum-qrl.com/security).

## Where to go next

If your question wasn't covered here, the complete 28-question reference is on the [FAQ page](https://quantum-qrl.com/faq), organized by category. For a broader technical grounding on the cryptography itself, start with [How XMSS Works](https://quantum-qrl.com/guides/how-xmss-works) or the [Quantum-Safe Wallet](https://quantum-qrl.com/quantum-safe-wallet) overview. The [full guides library](https://quantum-qrl.com/guides) covers installation, key management, and a full [2026 wallet review](https://quantum-qrl.com/guides/qrl-wallet-review-2026) in more depth, and [Safest Crypto Wallets 2026](https://quantum-qrl.com/safest-crypto-wallets-2026) covers wallet security more broadly if you're comparing options. Data-handling and usage terms are covered in the [Privacy Policy](https://quantum-qrl.com/privacy) and [Terms of Use](https://quantum-qrl.com/terms). For anything not covered anywhere in the documentation, including bug reports and responsible security disclosure, use the [Contact page](https://quantum-qrl.com/contact).

---

### Related articles

- [QRL Wallet Security and Audit History, Explained](qrl-wallet-security-audits-explained.md)
- [How to Download and Install QRL Wallet, Step by Step](how-to-download-install-qrl-wallet.md)
- [QRL vs Bitcoin: The Quantum Security Difference](qrl-vs-bitcoin-quantum-security.md)
- [About the QRL Foundation: Origins and Roadmap](about-qrl-foundation-history.md)
