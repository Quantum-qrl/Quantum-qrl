# QRL vs XRP: Are They Related?

This is one of the most common points of confusion in the space, and it's understandable why: QRL and XRP are three-letter tickers that look and sound alike, both refer to Layer-1-adjacent blockchain projects, and both come up in similar search queries. But they are entirely unrelated projects — different founders, different codebases, different technology, and different goals. This article clears up the confusion and covers the one dimension where the comparison is actually substantive: quantum resistance.

## Two separate projects, no relationship

QRL is the Quantum Resistant Ledger, a Layer-1 blockchain founded in 2016 by Dr. Peter Waterland and maintained today by the QRL Foundation, a Swiss non-profit, alongside Quantum Future Limited. Its mainnet launched in 2018. [QRL Wallet](https://quantum-qrl.com/) is the Foundation's official self-custodial wallet for it. Full project history is on the [About page](https://quantum-qrl.com/about).

XRP is the native asset of the XRP Ledger, a separate blockchain that launched in 2012, closely associated with Ripple. There is no corporate, technical, or funding relationship between QRL and Ripple or the XRP Ledger Foundation — the resemblance begins and ends with the ticker.

## The one comparison that actually matters: cryptography

Where the comparison becomes substantive rather than just a ticker-confusion clarification is signature security. QRL signs every transaction with XMSS, a hash-based post-quantum signature scheme standardized in NIST SP 800-208, and has done so since its 2018 genesis block — not as a later upgrade. The full mechanics of how and why that scheme resists quantum attacks are covered in [How XMSS Works](https://quantum-qrl.com/guides/how-xmss-works).

The XRP Ledger, by contrast, signs transactions with classical elliptic-curve cryptography — specifically ECDSA and Ed25519 — putting it in the same category as Bitcoin and Ethereum with respect to quantum vulnerability. A sufficiently large, fault-tolerant quantum computer running Shor's algorithm could, in principle, eventually break signatures secured this way. That's not a criticism unique to XRP; it describes the overwhelming majority of blockchains in production today. It's simply not the category QRL sits in.

To be clear about where things currently stand: there is no live post-quantum signature implementation in production on the XRP Ledger mainnet as of this writing. Engineers and community members associated with Ripple and the XRP Ledger have publicly discussed researching post-quantum signature schemes and a possible future migration path, but that work remains exploratory rather than shipped. This mirrors the broader pattern across most established chains — awareness of the eventual need, without a completed transition yet.

## What this means if quantum resistance is a priority for you

If protecting holdings against a future quantum-computing threat is something you're actively weighing, the practical guidance is straightforward: use a wallet on a chain whose signatures are already post-quantum today, rather than one with a future migration on the roadmap. QRL Wallet fits the first category — it signs with XMSS out of the box, so no future protocol upgrade is required for holdings to be quantum-resistant. XRP holdings, by contrast, still require an XRP Ledger wallet running on elliptic-curve cryptography, with no live post-quantum alternative currently available.

This same distinction — shipped versus promised — is the throughline across QRL's other comparison pages as well. [QRL vs Bitcoin](https://quantum-qrl.com/qrl-vs-bitcoin) covers the identical dynamic against the largest incumbent chain, and [Quantum-Resistant Cryptocurrencies, Compared](https://quantum-qrl.com/quantum-resistant-cryptocurrencies-list) surveys how several other projects — including ones with partial or testnet-stage post-quantum work — stack up against QRL's fully shipped implementation.

## Beyond the cryptography

Outside of signature security, QRL and XRP genuinely don't have much basis for comparison — different consensus mechanisms, different use cases, different communities. This article deliberately focuses on the one place where a real technical comparison exists, rather than manufacturing a broader rivalry between two projects that mostly just share confusable initials.

## If you're here for QRL specifically

If the quantum-resistance angle is what brought you here and you're evaluating QRL Wallet on its own merits, the [Security](https://quantum-qrl.com/security) page covers the full audit history (three independent reviews, most recently Halborn in March 2026 with zero cryptographic vulnerabilities found), and the [download page](https://quantum-qrl.com/download) has verified builds for every supported platform. The [FAQ](https://quantum-qrl.com/faq) also directly addresses the "is QRL related to XRP/Ripple" question and similar comparison queries in short form, and [Quantum-Safe Wallet](https://quantum-qrl.com/quantum-safe-wallet) lays out what genuinely constitutes post-quantum wallet security if you want the fuller technical case before deciding.

---

### Related articles

- [QRL vs Bitcoin: The Quantum Security Difference](qrl-vs-bitcoin-quantum-security.md)
- [Quantum-Resistant Cryptocurrencies, Compared](quantum-resistant-cryptocurrencies-compared.md)
- [How XMSS Hash-Based Signatures Actually Work](how-xmss-works-explained.md)
- [About the QRL Foundation: Origins and Roadmap](about-qrl-foundation-history.md)
