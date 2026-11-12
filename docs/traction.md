# Traction and delivery evidence

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
| Sumi studio | Signed | [LOI](https://drive.google.com/file/d/10DlUox3Taz-XvoLLq0ikuqSyQdjqLrpW/view)|
| Spreadless | Signed | [LOI](https://drive.google.com/file/d/1MaxCDAp9bzzllCSEduzwap2ZlEEeBzsB/view)|
| CoConnect | Signed | [LOI](https://drive.google.com/file/d/1KxcQ4g3e2vEkITHY2KoiM3KVuMLAeNt6/view)|

A letter of intent states a company's intention to pilot DoubleCheck; it is not a binding contract.

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
| Hosted frontend | <https://doublecheck-lime.vercel.app> |
| Public read model | wallet-free Soroban simulations from the browser |
| Intake | application/report webhook bridge in repository source; requires private deployment configuration |
| Independent security review | planned before mainnet |

The vNext test suite covers controller-consent onboarding, bounded renewal/mandates, personal-field
validation, immutable per-badge metadata authority, claim publication, strict confirmed mandate
evaluation, terminal and role-aware status changes, issuer-approved controller recovery, and
submitted keepalive behaviour.

The browser source includes a direct pair verifier, live iframe and share links, public credential
hash comparison, role-aware application/report intake, and an expert Freighter holder-write path.
None of those proves that a human verification operation is ready; testnet contract enforcement and
operational evidence quality are separate claims.

## Release distinction

The vNext testnet release now has:

1. rehearsed upgrade or clean deployment of the reviewed Wasm;
2. invariant and signed keepalive checks against deployed state;
3. regenerated binding from the final live contract specification;
4. frontend/API release with contract/network/webhook configuration verified; and
5. release evidence tying commit, Wasm hash, contract id, binding, and tests together.

The remaining release distinction is operational: controller acceptance exists in the ABI, while
browser issuer/acceptance workflows, staffed review, private evidence systems, and the independent
security review remain incomplete.

## Path to mainnet

- complete KYC/KYB review, evidence security, policies, notices, and appeals;
- resolve the privacy treatment of durable handles/hashes and on-chain claim free text;
- implement real credential proof-suite/selective-disclosure verification;
- operate an indexer/API, production RPC, monitoring, and signed TTL/restore process;
- complete issuer/arbiter/controller transaction UX, passkey recovery, and fee sponsorship; and
- complete the independent security review plus production key custody and incident drills.

The sequencing and exit criteria live in [Roadmap](roadmap.md); pilot success metrics are listed
there too. Current deployment evidence is in [Deployment](deployment.md#current-environments).
