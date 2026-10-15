# Marcus Richards

**I build guardrails for AI agents: the layer that decides what an agent may spend or do, for how long, and leaves a receipt either way.**
Calgary, Alberta 🇨🇦 · open to AI-safety and agent-infrastructure roles (remote, Calgary or relocation)

I started building with AI in June 2026. I direct AI coding agents and make the design calls myself: what a system guarantees, how it fails, and what counts as proof. Every repo below says what is verified, what is in progress, and what is not claimed.

*Built by Marcus Richards, directing AI coding agents.*

## Permit: authority between AI agents and money

[**Permit**](https://github.com/FetchDoge/permit) sits between an AI agent and PayPal. Before money moves it checks four clauses (budget, approved merchant, expiry, revocation), honours an e-stop, and writes a hash-chained receipt for every decision, allowed or blocked.

- **389 tests pass, 1 skipped** (`python -m pytest -q` at `21d7d7c`, matching green CI, Oct 15, 2026)
- `python demo.py` runs the six-beat mock demo with no credentials and no network, and ends with `ledger chain: VERIFIED`
- My entry in the [PayPal AI Hackathon](https://paypalaihackathon.devpost.com/), my first hackathon. The live sandbox run is still ahead, and the README says so.

## The lineage: how Permit got here

| | Repo | What it guarantees | Proof |
|---|---|---|---|
| Sep 27 | [**Interlock**](https://github.com/FetchDoge/interlock) | Authority is leased, not owned. Leases expire, a global e-stop revokes everything, and faults fail closed. Zero dependencies. | 68 tests, CI on Python 3.11–3.13 |
| Oct 2 | [**Permit**](https://github.com/FetchDoge/permit) | Interlock's leased-authority model applied to payments | 389 tests |
| Oct 6 | [**Governor**](https://github.com/FetchDoge/governor) | The same gate for *any* agent action: HMAC-signed expiring permits, a kill switch, a hash-chained receipt log and a signed forensics bundle | 27 tests |

> *Permit says what an agent may spend. Governor says what it may do. Interlock says for how long.*

**Outside check:** [**ep-aec-conformance**](https://github.com/FetchDoge/ep-aec-conformance) is a verifier for the IETF EP-AEC authorization-evidence draft, written from the spec text alone. It fails closed on every error, with 64 vectors (56 against -02, plus 8 selected -07 regressions). Writing it surfaced a defect in an older revision (-02), which the spec's maintainers confirmed. It had already been fixed in -03 ([discussion](https://github.com/emiliaprotocol/emilia-protocol/issues/864)).

## How I build

1. **Fail closed.** When something is ambiguous, deny and record why.
2. **Claims carry receipts.** Numbers in a README come with the command, the commit and the date.
3. **Agents don't hold credentials.** The authority check sits between intent and money.
4. **Attack your own work.** Merges are pinned to the reviewed commit, and a red-team method ([adversarial-seat](https://github.com/FetchDoge/adversarial-seat)) is chartered to change or kill agent-built work before it ships.

## Also built

- [**agentready**](https://github.com/FetchDoge/agentready): scores how well AI agents can read, cite and operate a website. 15 checks, one file, zero dependencies, with tests in CI ([live](https://FetchDoge.github.io/agentready/))
- [**Receipt Sorter**](https://github.com/FetchDoge/receipt-sorter): local-first receipt-to-ledger CLI with a validation layer that refuses to guess and provenance on every row. Stdlib-only Python. The demo got 15 of 15 fields right on 3 sample fixtures.
- [**Quote Rescue**](https://github.com/FetchDoge/quote-rescue): turns a contractor estimate into a decision pack that says "I don't know" where the quote is silent ([live demo](https://FetchDoge.github.io/quote-rescue/))
- [**Reclamation Evidence Ledger**](https://github.com/FetchDoge/reclamation-evidence-ledger): Sentinel-2 change detection on Alberta orphan-well sites. The README publishes that its screening results did **not** hold up under pre-registered testing ([dashboard](https://FetchDoge.github.io/reclamation-evidence-ledger/))
- [**Beacon**](https://github.com/FetchDoge/beacon) · [**Exhibit**](https://github.com/FetchDoge/exhibit) · [**Porcupine**](https://github.com/FetchDoge/porcupine): a funding radar, defensive OSINT and a defence-tender radar, each of which labels how every claim was sourced

<details>
<summary>Methods and specs</summary>

- [**The Register**](https://github.com/FetchDoge/the-register): this account's public-repo register, compiled from named checks, with a pre-push gate
- [**IntentSpec**](https://github.com/FetchDoge/intent-spec): a typed IR that compiles operator intent into existing agent machinery; the validator rejects drift
- [**interlock-forensics**](https://github.com/FetchDoge/interlock-forensics): a pre-registered provenance gate, one SHA-256-checkable file at a public tag
- [**agent-provenance-benchmark**](https://github.com/FetchDoge/agent-provenance-benchmark): a pre-registered provenance benchmark of ten popular agent frameworks, with a frozen rubric and two-lane sealed scoring
- [**Hermes Refuse**](https://github.com/FetchDoge/hermes-refuse): a design spec (no code yet) for a macOS execution layer that refuses ambiguous agent actions
- [**honestyield.dev**](https://github.com/FetchDoge/honestyield.dev): the honest-yield rule: no admitted before-and-after run pair, no savings number

</details>

## Foundations (June–August 2026)

The first two months were for learning how agents, builds and gates actually behave. Three lessons from them still hold up everything above:

- [**sovereign-contracts**](https://github.com/FetchDoge/sovereign-contracts) (Jul 27): I gated my own Hardhat compile/test/deploy path with Python checks. **Lesson:** a gate is only real if it can say no. That became fail-closed.
- [**star-lab**](https://github.com/FetchDoge/star-lab) (Aug 4): I ran and compared coding agents locally behind safety hooks and a health doctor. **Lesson:** an agent should never hold authority it can't lose. That became Interlock's leases, then Permit and Governor.
- [**fetchdoge-warehouse-system**](https://github.com/FetchDoge/fetchdoge-warehouse-system) and [**agent-job-board**](https://github.com/FetchDoge/agent-job-board): naming, audit and project-gate conventions for agent-built work. **Lesson:** if it isn't recorded, it didn't happen. That became the receipts.

## Get in touch

Open an issue on the relevant repo, or email [contact@marcusrichards.dev](mailto:contact@marcusrichards.dev).
