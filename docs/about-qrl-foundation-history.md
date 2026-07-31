# About the QRL Foundation: Origins and Roadmap

Understanding why [QRL Wallet](https://quantum-qrl.com/) exists and who's behind it helps explain design decisions that might otherwise look unusual — particularly the wallet's use of a signature scheme most other chains don't use. This is the project's history, its current stewardship, and where it's headed.

## The founding insight

QRL — the Quantum Resistant Ledger — was founded in 2016 by Dr. Peter Waterland. His starting observation was straightforward but, at the time, ahead of the broader industry conversation: Bitcoin's and Ethereum's cryptographic signature schemes, built on elliptic-curve mathematics, would eventually be vulnerable to sufficiently powerful quantum computers. Rather than treating that as a distant, hypothetical concern to address later, Waterland set out to build a blockchain that avoided the vulnerability from day one.

That decision led to QRL adopting XMSS (eXtended Merkle Signature Scheme), a hash-based signature algorithm, as its core cryptographic foundation — years before NIST would formally standardize it in SP 800-208. The technical detail of how that scheme works, and why it resists the quantum attacks that threaten elliptic-curve cryptography, is covered in [How XMSS Works](https://quantum-qrl.com/guides/how-xmss-works).

## Mainnet launch and what made it significant

QRL's mainnet launched in 2018, making it the first industrial blockchain implementation of XMSS in production. This is a meaningfully different claim from projects that have since added "quantum-resistant" as a marketing term without a comparable production track record — QRL's implementation has been running, signing real transactions, since before the term was even standardized by NIST. Every address on the chain, from the genesis block onward, has used this cryptography; it was never a later migration.

## Who maintains the project today

QRL is maintained by two organizations working alongside each other: the **QRL Foundation**, a non-profit based in Zug, Switzerland, and **Quantum Future Limited**. This structure — a dedicated non-profit foundation plus a limited company — is a common pattern in blockchain projects that need both a mission-oriented governance body and an operational entity capable of engaging in more conventional business activity. [QRL Wallet](https://quantum-qrl.com/) itself is the Foundation's official self-custodial wallet software, open source with signed releases published on GitHub (theQRL/qrl-wallet).

It's worth noting explicitly, because search confusion is common in this space: the official properties are **quantum-qrl.com** and **theqrl.org**. Other sites or apps using "QRL wallet" as a product name are not affiliated with the QRL Foundation.

## Security track record since launch

Since the 2018 launch, QRL's cryptographic implementation has been reviewed three separate times by three independent security firms — Red4Sec and x41 D-Sec in 2018, close to launch, and Halborn in March 2026, the most recent review, which found zero cryptographic vulnerabilities in the current post-quantum library. That cadence of repeated, independent review over eight years is covered in full on the [Security](https://quantum-qrl.com/security) page, and it's a meaningfully stronger signal than a single audit performed once and never revisited.

## The current network and its constraints

The current QRL mainnet runs proof-of-work consensus, with a maximum token supply of 105 million QRL. Its core strength — hash-based, post-quantum signature security — comes with a disclosed tradeoff: because XMSS is a stateful signature scheme, each address has a finite number of one-time signature keys (1,024 by default). The Foundation addresses this directly rather than obscuring it; the mechanics and practical management guidance are in [OTS Keys Explained](https://quantum-qrl.com/guides/ots-keys-explained).

It's also worth being precise about scope: QRL's transaction signing, fund custody, and consensus are fully quantum-resistant today, while the network's peer-to-peer layer (node identity, not custody) currently still uses classical cryptography, with post-quantum migration for that specific layer in active development as of 2026.

## Where the project is headed: QRL 2.0 and Project Zond

The Foundation's next-generation network, referred to as QRL 2.0 or Project Zond, is an EVM-compatible, Proof-of-Stake successor to the current proof-of-work mainnet. As of Q1 2026, it's in Testnet V2 and undergoing independent security audits ahead of a mainnet launch. This represents a significant architectural evolution — moving from proof-of-work to proof-of-stake and adding EVM compatibility — while preserving the post-quantum signature foundation that's been the project's defining characteristic since 2016.

## How this history informs the wallet you'd actually use

None of this history is abstract background if you're deciding whether to use [QRL Wallet](https://quantum-qrl.com/download) — it directly explains why the wallet behaves the way it does: why it uses XMSS instead of the elliptic-curve schemes most wallets use, why one-time signature keys exist at all, and why the Foundation has consistently chosen to disclose tradeoffs rather than smooth them over in marketing copy. For the practical side of using the wallet day to day, see [How to Install QRL Wallet](https://quantum-qrl.com/guides/qrl-wallet-download-guide) and the [FAQ](https://quantum-qrl.com/faq), or browse the [full guides library](https://quantum-qrl.com/guides). The site's [Privacy Policy](https://quantum-qrl.com/privacy) and [Terms of Use](https://quantum-qrl.com/terms) cover the legal specifics of using self-custodial software from the Foundation, and for support or responsible security disclosure, the [Contact page](https://quantum-qrl.com/contact) has the right channels.

---

### Related articles

- [QRL Wallet Security and Audit History, Explained](qrl-wallet-security-audits-explained.md)
- [QRL vs Bitcoin: The Quantum Security Difference](qrl-vs-bitcoin-quantum-security.md)
- [How XMSS Hash-Based Signatures Actually Work](how-xmss-works-explained.md)
- [QRL Wallet Review 2026](qrl-wallet-review-2026.md)
