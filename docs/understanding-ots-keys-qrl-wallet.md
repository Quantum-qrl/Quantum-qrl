# Understanding One-Time Signature (OTS) Keys

If you're coming from a Bitcoin or Ethereum background, one detail of [QRL Wallet](https://quantum-qrl.com/) will feel unfamiliar at first: your address doesn't have unlimited signing capacity. This article explains exactly why, what it means in practice, and how to manage it — because it's the one piece of quantum-resistant cryptography that actually changes user behavior, and it deserves a straight explanation rather than a footnote.

## Why this exists at all

QRL Wallet signs every transaction with XMSS, a hash-based signature scheme chosen specifically because it resists the kind of attack a large-scale quantum computer could eventually run against elliptic-curve cryptography. The tradeoff for that quantum resistance is that XMSS is a *stateful* scheme: it's built from a tree of one-time signature (OTS) key pairs, and each of those keys is only cryptographically safe to use once. The mechanics of the underlying Merkle tree structure are covered in [How XMSS Works](https://quantum-qrl.com/guides/how-xmss-works) — this article focuses specifically on what OTS keys mean for you as a wallet user.

By default, a QRL address is provisioned with 1,024 one-time signature keys. Every transaction you sign from that address consumes one of them. This isn't an arbitrary limitation bolted on top of the design — it's inherent to how hash-based signatures achieve their security guarantees, and QRL Foundation discloses it plainly rather than hiding it inside fine print, which is covered further on the [Security](https://quantum-qrl.com/security) page.

## What happens if you reuse or exhaust a key

Reusing an OTS key isn't just discouraged — the cryptography itself rejects it, and doing so anyway would begin leaking information that could theoretically let an attacker forge a signature from that key. QRL Wallet's design prevents key reuse by tracking which keys on an address have already been consumed.

The scenario that actually matters for a real user is exhaustion: if every one of the 1,024 keys on an address gets used up without the remaining balance being moved to a fresh address first, that address can no longer sign new transactions — and any funds left on it become permanently unspendable. This is the one meaningful tradeoff of XMSS's security model, and it's the reason QRL Wallet surfaces key usage in the interface rather than treating it as invisible plumbing.

## How to manage OTS keys in practice

For the overwhelming majority of users — anyone who isn't running thousands of transactions from a single address — this is a non-issue in day-to-day use. 1,024 signatures is a large number for typical wallet activity. The practical guidance is simple:

- **Keep an eye on remaining key count** as displayed in the wallet interface, particularly if you use one address for frequent, high-volume transactions.
- **Move remaining funds to a new address** before you get close to exhausting the current one's keys, rather than waiting until the last key is used.
- **Understand that this is a property of the address, not the wallet software** — generating a new address gives you a fresh set of 1,024 keys, at no cost and no loss of prior transaction history.

This is fundamentally different from, say, running out of storage on a device — it's a cryptographic property of the specific signature scheme, and it's the direct price of the quantum resistance that [XMSS](https://quantum-qrl.com/guides/how-xmss-works) provides. Compare that against Bitcoin's ECDSA, which has effectively unlimited signing capacity per address but no defense against a future large-scale quantum computer — the tradeoff is covered head-to-head in [QRL vs Bitcoin](https://quantum-qrl.com/qrl-vs-bitcoin).

## Why disclose this instead of designing around it

It's fair to ask why QRL doesn't just use a stateless post-quantum signature scheme instead, avoiding the OTS-key bookkeeping entirely. The honest answer is that XMSS was, at the time QRL launched in 2018 and remains today, one of the most thoroughly analyzed and standardized post-quantum signature families available — formalized in IETF RFC 8391 and NIST SP 800-208. QRL's three independent security audits (Red4Sec, x41 D-Sec, and Halborn) have specifically reviewed this stateful design, most recently in March 2026, finding zero cryptographic vulnerabilities. Choosing a well-audited, standardized scheme with a known, disclosed, manageable tradeoff over a newer or less-analyzed alternative is a defensible engineering decision, and it's one QRL Wallet is transparent about rather than obscuring.

## Getting started with this in mind

If you're setting up QRL Wallet for the first time, OTS key management doesn't need to change how you approach installation — the standard setup process, covered in [How to Install QRL Wallet](https://quantum-qrl.com/guides/qrl-wallet-download-guide), applies the same way. It's simply worth knowing this detail exists before you start transacting heavily from a single address, particularly if you're using the wallet for frequent purchases via the [in-wallet card buying feature](https://quantum-qrl.com/buy).

For a broader technical grounding, [How XMSS Works](https://quantum-qrl.com/guides/how-xmss-works) explains the Merkle tree structure that OTS keys are built from, and the [Security](https://quantum-qrl.com/security) page covers how this fits into QRL Wallet's overall security architecture. See the independent [QRL Wallet Review 2026](https://quantum-qrl.com/guides/qrl-wallet-review-2026) for how this tradeoff is weighed against the wallet's strengths, and [Safest Crypto Wallets 2026](https://quantum-qrl.com/safest-crypto-wallets-2026) for how it compares to wallet security more broadly. Common OTS-related questions are also answered directly in the [FAQ](https://quantum-qrl.com/faq), the [Terms of Use](https://quantum-qrl.com/terms) cover the liability implications of self-managed keys, and the [homepage](https://quantum-qrl.com/) has the broader overview of what QRL Wallet does.

---

### Related articles

- [How XMSS Hash-Based Signatures Actually Work](how-xmss-works-explained.md)
- [QRL Wallet Security and Audit History, Explained](qrl-wallet-security-audits-explained.md)
- [How to Download and Install QRL Wallet, Step by Step](how-to-download-install-qrl-wallet.md)
- [QRL vs Bitcoin: The Quantum Security Difference](qrl-vs-bitcoin-quantum-security.md)
