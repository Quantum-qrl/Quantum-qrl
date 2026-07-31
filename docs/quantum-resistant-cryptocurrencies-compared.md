# Quantum-Resistant Cryptocurrencies, Compared

"Quantum-resistant" has become one of the more overused phrases in crypto marketing, applied to everything from chains with a shipped post-quantum signature scheme to chains with a single roadmap sentence about eventually looking into it. This article sorts through what's actually implemented today versus what's planned, using [QRL Wallet](https://quantum-qrl.com/) and the Quantum Resistant Ledger as the reference point for a fully shipped implementation.

## Why this distinction matters

The threat these projects are all nominally addressing is the same: a sufficiently large, fault-tolerant quantum computer running Shor's algorithm could eventually break the elliptic-curve and RSA-based cryptography that secures the overwhelming majority of blockchains in production, including Bitcoin and Ethereum. That threat isn't imminent — such a machine doesn't currently exist at the necessary scale — but cryptographic migrations at blockchain scale take years to plan, test, and execute even once the need is clear. That's exactly why the shipped-versus-planned distinction matters: a project that's already made the transition has years of production hardening that a project still in research or testnet doesn't.

## QRL: the longest-running shipped implementation

The Quantum Resistant Ledger launched its mainnet in 2018 as the first industrial implementation of XMSS (eXtended Merkle Signature Scheme), a hash-based signature algorithm later standardized by NIST in SP 800-208 and by IETF in RFC 8391. Every QRL address, from the genesis block forward, has been signed this way — it's not a migration applied to an existing chain, it's the chain's original design. The mechanics of how XMSS achieves quantum resistance are covered in [How XMSS Works](https://quantum-qrl.com/guides/how-xmss-works), and the practical tradeoff it involves — one-time signature keys with finite per-address capacity — is covered honestly in [OTS Keys Explained](https://quantum-qrl.com/guides/ots-keys-explained) rather than glossed over.

## Where other projects stand

A handful of other projects have made real, if differently-scoped, moves in this direction:

**IOTA** uses Winternitz one-time signatures at the transaction level — a hash-based scheme in the same broad family as XMSS, though implemented differently and with its own tradeoffs around address reuse.

**Algorand** applies Falcon-based signatures, a lattice-based post-quantum scheme, specifically to its state proofs rather than to every standard transaction — a narrower scope of post-quantum coverage than a chain that signs all transactions this way.

**QANplatform** is building a post-quantum smart contract layer, positioning itself around post-quantum security for a newer, EVM-adjacent execution environment.

Coverage and maturity differ meaningfully between these approaches — some cover transaction signing broadly, others cover a narrower subset of network operations, and the level of independent audit and years-in-production varies considerably across all of them. None currently combines QRL's specific combination of full-transaction hash-based signing since genesis, multiple independent security audits, and eight years of mainnet operation.

## Where Bitcoin, Ethereum, and XRP sit

For contrast, it's worth being clear about where the largest chains currently stand rather than assuming. Bitcoin and Ethereum both sign with ECDSA, squarely in the vulnerable category, though both developer communities are aware of the long-term risk and have discussed post-quantum proposals without a shipped implementation yet — the fuller comparison against Bitcoin specifically is in [QRL vs Bitcoin](https://quantum-qrl.com/qrl-vs-bitcoin). The XRP Ledger signs with classical ECDSA and Ed25519 as well, with no live post-quantum implementation in production, despite public discussion of future research — covered in detail in [QRL vs XRP](https://quantum-qrl.com/qrl-vs-xrp).

## What "quantum-resistant" should actually mean when you evaluate a project

Given how loosely the term gets applied, a few concrete questions are more useful than the label itself:

- **Is the post-quantum scheme live on mainnet today, or planned for a future upgrade?**
- **Does it cover all transaction signing, or a narrower subset of operations?**
- **Has the implementation been independently audited, and how recently?**
- **How long has it actually been running in production, under real economic value?**

QRL's answers — live since 2018 genesis, covers all transaction signing, three independent audits including one as recently as March 2026, eight years in production — are the specific claims worth checking rather than taking on faith. The broader framework for evaluating any wallet's quantum-safety claims, not just QRL's, is laid out in [Quantum-Safe Wallet](https://quantum-qrl.com/quantum-safe-wallet).

## Trying QRL directly

If this comparison has you interested in the reference implementation itself, [QRL Wallet](https://quantum-qrl.com/download) is available for Windows, macOS, Linux, iOS, and Android, with in-wallet card purchases covered in [How to Buy QRL Coin](https://quantum-qrl.com/buy). The [Security](https://quantum-qrl.com/security) page has the full audit history, and the [FAQ](https://quantum-qrl.com/faq) covers common comparison questions across all of these projects in short form.

---

### Related articles

- [QRL vs Bitcoin: The Quantum Security Difference](qrl-vs-bitcoin-quantum-security.md)
- [QRL vs XRP: Are They Related?](qrl-vs-xrp-are-they-related.md)
- [How XMSS Hash-Based Signatures Actually Work](how-xmss-works-explained.md)
- [The Safest Crypto Wallets in 2026: What Actually Counts](safest-crypto-wallets-2026-guide.md)
