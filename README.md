# Marcus Richards

**I build guardrails for AI agents: spending limits, expiring authority, and a receipt for every claim.**
Calgary, Alberta 🇨🇦

Agents are getting wallets, shells and credentials. I build the layer in between: what an agent is *allowed* to do, for how long, and what record it leaves. I prefer local-first tools with few dependencies, and READMEs that say what is proven and what isn't.

## Flagship projects

| Project | What it guarantees | Try it |
|---|---|---|
| [**Permit**](https://github.com/FetchDoge/permit) | Enforces spend caps, merchant allowlists, expiry, revocation and an e-stop between AI agents and PayPal. Every decision writes a hash-chained receipt | `python demo.py` (mock mode, no credentials, no network) |
| [**Interlock**](https://github.com/FetchDoge/interlock) | Bounds agent authority with expiring leases, a global e-stop, a fault bus and provenance-stamped claims. The gate fails closed. Zero-dependency Python, installed from source (not on PyPI) | `git clone https://github.com/FetchDoge/interlock && cd interlock && pip install -e ".[test]" && pytest -q` |
| [**Governor**](https://github.com/FetchDoge/governor) | Gates every agent action on an HMAC-signed, expiring permit, with a kill switch and a hash-chained receipt log | `pip install -e . && pytest -q` |
| [**Receipt Sorter**](https://github.com/FetchDoge/receipt-sorter) | A local-first receipt sorter that shows its work: local Gemma extraction, a validation layer, and provenance on every ledger row. Stdlib-only Python | See the repo README for setup |
| [**Reclamation Evidence Ledger**](https://github.com/FetchDoge/reclamation-evidence-ledger) | Watches Alberta orphan-well reclamation from orbit and stamps every claim with provenance, uncertainty and limits. Its README carries a 2026-10-09 notice: the screening results did not hold up under pre-registered testing | [live dashboard](https://FetchDoge.github.io/reclamation-evidence-ledger/) |
| [**EP-AEC conformance**](https://github.com/FetchDoge/ep-aec-conformance) | Verifies EP-AEC evidence chains from the spec text alone and fails closed on every error. Building it exposed a bypass in the spec ([discussion](https://github.com/emiliaprotocol/emilia-protocol/issues/864)) | `python3 -m pytest tests/test_conformance.py` |
| [**agentready**](https://github.com/FetchDoge/agentready) | Scores any website on how well AI agents can read, cite and operate it: 15 checks, one file, zero dependencies | `node scan.mjs yoursite.com` · [scan my site via an issue](https://github.com/FetchDoge/agentready/issues/new?title=Scan%20my%20site&body=My%20website%20is%3A%20https%3A%2F%2F) |

> *Permit says what an agent may spend. Governor says what it may do. Interlock proves what it did.*

<details>
<summary>More: tools, specs, methods and research</summary>

- [**Quote Rescue**](https://github.com/FetchDoge/quote-rescue): turns a contractor quote into a decision pack that says "I don't know" where the quote was silent ([live demo](https://FetchDoge.github.io/quote-rescue/))
- [**Beacon**](https://github.com/FetchDoge/beacon): funding radar for Calgary, Alberta and Canada builders; every program carries a claim tier ([live](https://FetchDoge.github.io/beacon/))
- [**Exhibit**](https://github.com/FetchDoge/exhibit): defensive OSINT that refuses out-of-scope targets unless attested; every finding is a sourced, tiered claim
- [**Sovereign Contracts**](https://github.com/FetchDoge/sovereign-contracts): a local Hardhat 3 compile/test/coverage/deploy path with invariant tests, no cloud accounts
- [**Star Lab**](https://github.com/FetchDoge/star-lab): a local control plane for coding agents with memory, a deny list under always-approve, and a health doctor
- [**IntentSpec**](https://github.com/FetchDoge/intent-spec): a typed IR that compiles operator intent into existing agent machinery
- [**The Adversarial Seat**](https://github.com/FetchDoge/adversarial-seat): a standing red-team method for agent-built work, with a worked example
- [**The Register**](https://github.com/FetchDoge/the-register): this account's public-repo register, compiled from named checks
- [**Agent Job Board**](https://github.com/FetchDoge/agent-job-board): run AI agents like a company — roles, project gates, and an append-only ledger
- [**interlock-forensics**](https://github.com/FetchDoge/interlock-forensics): pre-registration for the AEGIS Day-30 provenance gate
- [**Hermes Refuse**](https://github.com/FetchDoge/hermes-refuse): design spec (no code yet) for a macOS execution layer that refuses ambiguous agent actions
- [**honestyield.dev**](https://github.com/FetchDoge/honestyield.dev): the honest-yield rule, "no pair, no number"

</details>

## How I build

1. **Fail closed.** When something is ambiguous, deny and record why.
2. **Claims carry receipts.** A README says what is verified, what is in progress, and what is not claimed.
3. **Agents don't hold credentials.** The authority check sits between intent and money.

## Evidence

Every number below was checked against a live run or the project record on the date shown:

- **Permit:** 389 tests passed, 1 skipped (390 collected), in a full suite run at commit `21d7d7c`, matching the green CI run on that commit, 2026-10-15.
- **EP-AEC conformance:** 64 test vectors; 64/64 passed against the -07 draft, with the result confirmed by the specification's author, 2026-10-13.
- **Receipt Sorter:** demo verified 2026-10-13 — 15 of 15 fields correct across 3 sample fixtures (see the repo's `demo/RESULTS.md`).

Numbers that could not be re-verified are not listed. Each repo's README cites where its own numbers come from.

## Now

- **Permit** for the [PayPal AI Hackathon](https://paypalaihackathon.devpost.com/) (deadline Nov 12, 2026)
- **Receipt Sorter** — released 2026-10-13: [repo](https://github.com/FetchDoge/receipt-sorter)
- **[interlock-forensics](https://github.com/FetchDoge/interlock-forensics)**: pre-registered provenance benchmark, gate 2026-10-27

## Get in touch

Found a bug or have a question? Open an issue on the relevant repo. For anything else: [contact@marcusrichards.dev](mailto:contact@marcusrichards.dev).
