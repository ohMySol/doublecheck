# Traction

Eight pilot companies have signed letters of intent to use DoubleCheck, backed by Jobited's network of 23 company relationships.

The Stellar testnet contract is live and publicly inspectable; its 5 entities and 8 claims are
demonstration data.

## Letters of intent

Redacted letters of intent from pilot companies. Each is published with the signatory's permission.

| Company | Status | Letter |
|---|---|---|
| Peridot Finance | Signed | [LOI](https://drive.google.com/file/d/1gN9l8--Qtyyqs4mhTjzOtlGYPdA0rWir/view?usp=drivesdk)|
| Payroutes | Signed | [LOI](https://drive.google.com/file/d/1_q7_jIpSgFglWWEcAGGEA_bb2ZbhnHG3/view)|
| Wintrader | Signed | [LOI](https://drive.google.com/file/d/17cV6Qker9WTMkTUHt9XvE6Tu1HpMZBtA/view)|
| GuardianStack | Signed | [LOI](https://drive.google.com/file/d/1TPmFEHq7Y-PR5SNnvTgQOWd-UUHI0Mlk/view)|
| USD8 | Signed | [LOI](https://drive.google.com/file/d/1zxzLvbo7hmdeM9-sfiI9KMIC5a9hk9wA/view)|
| Sumi Studio | Signed | [LOI](https://drive.google.com/file/d/10DlUox3Taz-XvoLLq0ikuqSyQdjqLrpW/view)|
| Spreadless | Signed | [LOI](https://drive.google.com/file/d/1MaxCDAp9bzzllCSEduzwap2ZlEEeBzsB/view)|
| CoConnect | Signed | [LOI](https://drive.google.com/file/d/1KxcQ4g3e2vEkITHY2KoiM3KVuMLAeNt6/view)|

A letter of intent states a company's intention to pilot DoubleCheck; it is not a binding contract.

## Jobited network

DoubleCheck is built by Jobited. These figures describe Jobited's own recruiting network as of
9 November 2026.

| Metric | Figure |
|---|---|
| Company relationships | 23 |
| Active recruiting mandates | 8 |
| Technical professionals | 2,500, of whom 2,000 are outside Germany |

The 2,500 counts technical professionals whom Jobited has vetted and who are active in its network.
The 4,672 registered talents shown on onchainhires.com count every registered profile, which is why
the two numbers differ.

## Launch floor

The launch floor is the minimum DoubleCheck needs at launch. These are targets, not current figures.

| Target | Launch floor |
|---|---|
| Verified companies | 7 |
| Confirmed relationships | 22 |
| Mandates | 5 |

## Inspectable delivery

| Evidence | Current state |
|---|---|
| Source licence | Apache 2.0 |
| Repository contract | vNext; passing test suite; optimized Wasm below the 128 KiB limit |
| Public contract | vNext Stellar testnet address `CDY4WIUWUJWDW4AKPTYFXTRONQQVS52PS2ZYFU2S5HEMW2U7LM5KRHKP` |
| Contract explorer | [stellar.expert](https://stellar.expert/explorer/testnet/contract/CDY4WIUWUJWDW4AKPTYFXTRONQQVS52PS2ZYFU2S5HEMW2U7LM5KRHKP) |
| Public Wasm | 60,131 bytes; SHA-256 `1ab20ff8c30b0f704b64dee4aed5d1dd111e5b24e33fb612ef9309aef5dc895a` |
| Public contract demo data | 5 entities and 8 claims; demonstration data only |
| Hosted frontend | [doublecheck-lime.vercel.app](https://doublecheck-lime.vercel.app) |
| Public read model | wallet-free Soroban simulations from the browser |
| Intake | application/report webhook bridge in repository source; requires private deployment configuration |
| Independent review | planned before mainnet |

The vNext test suite covers controller-consent onboarding, bounded renewal/mandates, personal-field
validation, immutable per-badge metadata authority, claim publication, strict confirmed mandate
evaluation, terminal and role-aware status changes, issuer-approved controller recovery, and
submitted keepalive behaviour.

## Live now and next

**Live on Stellar testnet and in the hosted frontend:**

- the vNext registry contract, with controller-consent onboarding, bounded renewal and mandates, and
  strict confirmed-mandate evaluation;
- a wallet-free verifier: direct pair check, live iframe and share links, and public credential hash
  comparison;
- role-aware application and report intake; and
- an expert Freighter holder-write path.

**Delivered with the grant tranches:**

| Tranche | What it adds | Target date |
|---|---|---|
| 1 · MVP | Company root of trust and wallet-connected issuer console; passkey accounts and sponsored Soroban transactions | 29 December 2026 and 11 January 2027 |
| 2 · Testnet | Contract governance, registry indexer, public API, SDK and public metrics; Soroban TTL keeper and restoration service; signed credential and commitment layer | 30 January to 22 February 2027 |
| 3 · Mainnet | Production hardening and custody; open-source v1.0 and reproducible deployment; mainnet launch with the Jobited issuance floor and user acceptance testing | 10 March to 15 April 2027 |

The full deliverable plan is in [Stellar technical architecture](../technical/stellar-architecture.md#13-grant-delivery-plan).

## Release distinction

The vNext testnet release now has:

1. rehearsed upgrade or clean deployment of the reviewed Wasm;
2. invariant and signed keepalive checks against deployed state;
3. regenerated binding from the final live contract specification;
4. frontend/API release with contract/network/webhook configuration verified; and
5. release evidence tying commit, Wasm hash, contract id, binding, and tests together.

The remaining release distinction is operational: controller acceptance exists in the ABI, while
browser issuer/acceptance workflows, staffed review, private evidence systems, and the independent
review remain incomplete.

## Path to mainnet

- complete KYC/KYB review, evidence security, policies, notices, and appeals;
- resolve the privacy treatment of durable handles/hashes and on-chain claim free text;
- implement real credential proof-suite/selective-disclosure verification;
- operate an indexer/API, production RPC, monitoring, and signed TTL/restore process;
- complete issuer/arbiter/controller transaction UX, passkey recovery, and fee sponsorship; and
- complete the independent review plus production key custody and incident drills.

The sequencing and exit criteria live in [Roadmap](roadmap.md); pilot success metrics are listed
there too. Current deployment evidence is in [Deployment](../technical/deployment.md#current-environments).
