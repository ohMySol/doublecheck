# Project introduction

![DoubleCheck](https://github.com/user-attachments/assets/22f83114-c2ff-45d0-b3a2-bc6085259e3c)

Trust infrastructure that lets a company cryptographically confirm the people and organisations authorised to represent it.

DoubleCheck answers three questions from one public link: is this subject verified, is the stated relationship supported, and is there a confirmed mandate that is valid now? A reader needs no wallet or account.

| Directory                | Purpose                                            |
| ------------------------ | -------------------------------------------------- |
| [`SC/`](technical/sc.md) | Soroban registry contract (Rust)                   |
| [`FE/`](technical/fe.md) | React/Vite verifier plus Vercel intake function    |
| [`docs/`](docs.md)       | Architecture, operations, development, and roadmap |

### Trust flow

1. A recruiter, agency, or hiring company submits an off-chain application. The issuer completes manual KYC/KYB and evidence review outside the public ledger.
2. The issuer proposes a badge on-chain. Its intended Stellar controller must explicitly accept it before the badge becomes active. Proposals expire within 30 days; active badges expire within 400 days and require periodic re-verification.
3. An organisation controller, subject controller, or issuer records relationships and mandates. The signer determines whether a claim is self-asserted, counterparty-confirmed, or issuer-confirmed.
4. `is_authorised` returns true only for an active, unexpired pair with a currently valid confirmed mandate. A self-asserted mandate is visible evidence, never authority. A linked relationship must also match the parties, be published with subject/admin consent, and remain active.
5. Suspension, withdrawal, completion, expiry, and revocation take effect at verification time. Revocation and withdrawn/ended terminal states cannot be silently reversed.

Natural-person names and verification evidence stay in off-chain credentials so issuer-controlled storage can support deletion. The chain contains addresses, handles, timestamps, hashes, and currently also short relationship/mandate text; those anchors and any third-party copies or caches are not guaranteed erasable, and the free text remains a privacy/legal design issue.

### Run locally

```bash
cd FE
npm install
npm run dev
```

Public reads use Stellar testnet without a wallet. Application and report delivery additionally requires the server-only `INTAKE_WEBHOOK_URL`; when it is absent the API returns an honest `503` and does not pretend a submission was received. See [`FE/README.md`](technical/fe.md).

```bash
cd SC
cargo test
stellar contract build --optimize
```

The explorer provides shareable handle links, QR codes, neutral HTML/Markdown links, and a live iframe at `/badge/<handle>`. All resolve or re-read current registry state instead of freezing a "verified" result that could outlive a revocation.

### Deployment status

The repository and public Stellar testnet contract now run the **vNext interface**, including controller-consent onboarding, bounded annual renewal, issuer-controlled metadata anchors, stricter mandate authorisation, role-aware status transitions, and signed batched keepalive. Its contract suite passes, and the optimized Wasm is below Stellar's 128 KiB contract limit.

The existing address was upgraded in place on 10 August 2026. Its 5 demonstration entities and 8 claims were preserved, and the checked-in TypeScript binding was regenerated from the upgraded live specification. This is still testnet, not a production release.

| Resource | Value |
|---|---|
| Hosted explorer | [doublecheck-lime.vercel.app](https://doublecheck-lime.vercel.app) |
| vNext testnet contract | `CDY4WIUWUJWDW4AKPTYFXTRONQQVS52PS2ZYFU2S5HEMW2U7LM5KRHKP` |
| Wasm SHA-256 | `1ab20ff8c30b0f704b64dee4aed5d1dd111e5b24e33fb612ef9309aef5dc895a` |
| Contract explorer | [stellar.expert](https://stellar.expert/explorer/testnet/contract/CDY4WIUWUJWDW4AKPTYFXTRONQQVS52PS2ZYFU2S5HEMW2U7LM5KRHKP) |
| Demonstration data | 5 entities and 8 claims |

### Documentation

* [`docs/README.md`](docs.md) — documentation index and sources of truth
* [`docs/stellar-architecture.md`](technical/stellar-architecture.md) — Stellar/Soroban technical architecture: the four registries, storage and TTL, event schema and indexer, passkey smart accounts, wallets, sponsored transactions, SEP-10/SEP-45, governance, and the off-chain credential layer
* [`docs/architecture.md`](technical/architecture.md) — data, trust, privacy, and Stellar design
* [`SC/README.md`](technical/sc.md) — contract interface and release workflow
* [`FE/README.md`](technical/fe.md) — frontend, verifier, intake API, and bindings
* [`docs/deployment.md`](technical/deployment.md) — release and operations runbook
* [`docs/DEVELOPMENT.md`](technical/development.md) — contributor workflow
* [`docs/REPOSITORY.md`](technical/repository.md) — repository ownership map
* [`docs/roadmap.md`](product/roadmap.md) — release gates and remaining product work
* [`SECURITY.md`](policy/security.md) — security boundary and reporting

### Status

Pre-production. Mainnet is blocked on full KYC/KYB operations, complaint and appeals policy,
production key custody, credential proof/selective-disclosure design, operational indexing and TTL
maintenance, and an independent review. Browser extension, passkey account abstraction,
fee sponsorship, and production write dashboards are not complete.

### Maintainers

DoubleCheck is built by Jobited. Core team of four.

- **Luis Homann**, Founder and Ecosystem Lead. Runs Jobited's Web3 and blockchain recruiting; sources pilot companies, recruiters and hiring mandates; owns relationship and trust policy design and pilot coordination. [LinkedIn](https://www.linkedin.com/in/luis-homann/)
- **Nuno David**, Full-Stack and Smart Contract Engineer. Rust and Solidity across EVM and Cosmos. At Escher Finance led refactors of a chain-abstracted liquid staking hub on Babylon (multimillion USD TVL) and designed a tokenized vault in CosmWasm. Open source contributor with merged PRs in Foundry, viem and revm. Expertise in zk-SNARKs, ranked top 200 on cryptohack.org. [GitHub](https://github.com/ndavd) · [LinkedIn](https://www.linkedin.com/in/ndav)
- **Anton Holovchenko**, smart contract engineer with 3+ years of experience building DeFi protocols across Ethereum and EVM ecosystems, with a focus on lending, staking, and yield strategies. He has designed cross-chain lending systems, migrated tokens to LayerZero standards, and built staking and launchpool infrastructures with integrated reward mechanisms. His background also includes independent review, oracle integrations, and strong testing practices, ensuring robust and scalable on-chain systems. [GitHub](https://github.com/ohMySol) · [LinkedIn](https://www.linkedin.com/in/anton-holovchenko/)
- **Alexandre Hebert**, Head of APAC Growth and Partnerships. Connects top tech talent with fintech companies from Singapore. Scaled Local Expats Bali from 60 to 400+ members; co-owned and grew multi-location businesses in Canada. Deep experience in partnerships, sales operations and client onboarding. Alexandre will be responsible to help partners integrate DoubleCheck easily. [LinkedIn](https://www.linkedin.com/in/alexandrehebert-11549224)

### Licence

Apache 2.0 — see [`LICENSE`](LICENSE/).
