---
name: pre-motion
description: Runs an adversarial premortem on a UK litigation matter. Synthesises the lost version of the case and runs a structured multi-agent analysis on why it lost — procedural, substantive, evidentiary, strategic failure modes. Returns a stress-test brief with ranked failure scenarios, evidence inconsistencies, blind spots, mitigations, and one brutal one-sentence verdict. Use when the user wants to stress-test a case before issue, before settlement negotiations, before a litigation funder pitch, or before deciding whether to take a case. Triggers include "pre-motion", "stress-test this case", "where does this lose", "adversarial premortem", "premortem this litigation", "weakest version", "find the holes".
argument-hint: "[--depth=fast|thorough]"
---

# /pre-motion

1. Load the matter context: facts, evidence references, claim heads, pleaded position, and the strongest version of the case as the user sees it.
2. Run the adversarial pipeline:
   - **Stage 1 — Optimistic Analyst.** The strongest version of the case the evidence supports.
   - **Stage 2 — Evidence Inspector** (parent + three parallel sub-agents: document review, cross-reference, chronology). Returns merged evidence flags with severity.
   - **Stage 3 — Premortem Adversary** (parent + four parallel Opus sub-agents: procedural, substantive, evidentiary, strategic). Each instructed: "It is [trial date + 1 year]. The case has been LOST. Walk back." Returns ranked failure scenarios per category.
   - **Stage 4 — Synthesiser.** Diffs the optimistic case against the adversarial findings.
3. Output: verdict (steelman / borderline / strawman), ranked failure scenarios, evidence inconsistencies, blind spots, mitigations, and the one brutal sentence: "if we lose this, this will be why."

---

# Pre-Motion — adversarial premortem for UK litigation

## Purpose

You think you've built the strongest version of your case. Pre-Motion runs it through a structured adversarial pipeline to find where it actually loses — the procedural, substantive, evidentiary, and strategic failure modes opposing counsel will pull on first.

The opposite of confirmation bias. The opposite of optimistic case theory. By design.

For: solicitors stress-testing before issue, in-house counsel before signing off, mediators evaluating settlement value, litigation funders pricing a matter, anyone deciding whether to take a case.

## Architecture

```
Orchestrator
│
├── Stage 1 · Optimistic Analyst                  (single agent — Sonnet)
│     The strongest version of the case the evidence supports.
│
├── Stage 2 · Evidence Inspector                  (parent + 3 parallel sub-agents — Sonnet)
│     ├── Document review sub-agent
│     ├── Cross-reference sub-agent
│     └── Chronology sub-agent
│     Output: merged evidence flags with severity.
│
├── Stage 3 · Premortem Adversary                 (parent + 4 parallel sub-agents — Opus)
│     ├── Procedural sub-agent
│     ├── Substantive sub-agent
│     ├── Evidentiary sub-agent
│     └── Strategic sub-agent
│     Each instructed: "It is [date]. The case has been LOST. Walk back."
│     Output: ranked failure scenarios per category.
│
└── Stage 4 · Synthesiser                         (single agent — Sonnet)
      Diffs the optimistic case against the adversarial findings.
      Produces the brief.
```

Seven LLM calls under the hood. Two parallel `asyncio.gather` blocks (Stage 2 sub-agents, Stage 3 sub-agents). End-to-end runtime ~2-3 minutes on a real case at `--depth=thorough`; ~30 seconds at `--depth=fast` (Stage 3 runs Sonnet instead of Opus).

## Inputs

- Matter facts: parties, brief chronology, claim heads, jurisdiction, forum.
- Evidence references: documents, witness statements, expert reports — pointers to matter content, not re-uploaded.
- The strongest version of the case as the user sees it (the optimistic baseline).
- Optional: counterparty's pleaded defence or anticipated defence.
- Optional: depth flag (`--depth=fast` for ~30s preview; `--depth=thorough` for the full ~3min run).

## Failure-mode categories

The four Stage 3 sub-agents specialise in the four ways UK civil cases lose.

### Procedural

- Limitation expired or contested (Limitation Act 1980, s.5 / s.11 / s.14A).
- Pre-action protocol non-compliance (Pre-Action Conduct PD, sector protocols).
- Strike-out or summary judgment vulnerability (CPR 3.4, CPR 24).
- Costs sanctions risk (CPR 44.2).
- ADR refusal exposure (Halsey, Churchill v Merthyr Tydfil [2023]).
- Service / jurisdiction defects (CPR 6).
- Disclosure-regime missteps (CPR 31 vs PD 57AD).

### Substantive

- Cause-of-action elements unproven.
- Causation gaps (factual or legal — *Wagon Mound*, *Fairchild*, *SAAMCO*).
- Mitigation failures (*British Westinghouse*).
- Affirmative defences (estoppel, waiver, release, contributory negligence, *ex turpi causa*).
- Statutory bars (Consumer Rights Act, UCTA, statutory limitation).

### Evidentiary

- Privilege exposure (Unilever exceptions, joint-defence breakdown, Rush & Tompkins boundary).
- Disclosure failures and adverse-inference risk (CPR 31, PD 57AD).
- Witness credibility / availability / inconsistency.
- Hearsay weaknesses (Civil Evidence Act 1995 s.2-4 notice failures).
- Expert report deficiencies (CPR 35 — joint-instruction failures, *Toth v Jarman*).
- Document authenticity / chain of custody.

### Strategic

- Settlement leverage misjudged (BATNA gap to opposing side).
- Costs/benefit ratio misaligned with client objectives.
- Reputational / regulatory exposure from issue or trial.
- Information asymmetry working against the client.
- Counterparty's BATNA stronger than the optimistic baseline assumes.

## Workflow

### Step 1 — CPR 31.22 + privilege gate

Pre-Motion reads matter documents to build the optimistic baseline and stress-test evidence. If documents are from disclosure in current proceedings, the matter slug must match the proceedings reference (recorded on the matter). If from disclosure in *different* proceedings, refuse until permission, agreement, or open-court reference is established.

Privilege posture also applies: a `C_paused` matter refuses Pre-Motion entirely. A `B_mixed` matter runs but the output includes a `[PRIVILEGE FLAGGED]` banner and recommends counsel review before any external distribution.

### Step 2 — Optimistic baseline

Stage 1 reads the matter facts and evidence references and builds the strongest version of the case. This becomes the foil for Stages 2 and 3.

### Step 3 — Evidence inspection (parallel)

Three sub-agents in parallel:
- Document review: gaps, inconsistencies, weak documents.
- Cross-reference: claims in one document contradicted by another.
- Chronology: timeline gaps, dates that don't fit, missing events.

Merged into a single evidence-flags list with severity per flag.

### Step 4 — Premortem adversary (parallel)

Four sub-agents in parallel, each in its category. Each is given the same setup prompt: *"It is [trial date + 1 year]. The case described above has been LOST. Walk back: what failure modes in your category caused the loss?"*

Each returns ranked failure scenarios with severity and likelihood. Sub-agent prompts incorporate the relevant authority for the category (CPR rules for procedural; substantive law citations for substantive; etc.).

### Step 5 — Synthesise

Stage 4 diffs the optimistic baseline against the adversarial findings. Produces the brief with verdict, ranked scenarios, evidence inconsistencies, blind spots, mitigations, and the one brutal sentence.

## Output

```
[Reviewer note: work product, prepared in contemplation of litigation, subject to litigation privilege.]

# Pre-Motion brief — [Matter name]

**Date generated:** [YYYY-MM-DD]
**Depth:** fast | thorough
**Privilege posture:** A_cleared | B_mixed | C_paused
**Verdict:** [Steelman | Borderline | Strawman]

## The one brutal sentence

"If we lose this, this will be why: [single sentence]"

## Optimistic baseline

[The strongest version of the case, as Stage 1 built it.]

## Ranked failure scenarios

### Procedural
1. [Scenario, one paragraph.] Severity: H/M/L. Likelihood: H/M/L. Mitigation: [...]
2. [...]
3. [...]

### Substantive
1. [...]

### Evidentiary
1. [...]

### Strategic
1. [...]

## Evidence inconsistencies

[Flagged by Stage 2.]

## Blind spots

[Issues the optimistic baseline assumed resolved that Stage 3 found unresolved.]

## Mitigations

[Concrete actions before the next case milestone: strengthen evidence, amend pleadings, settle, withdraw, brief counsel differently. One per scenario where applicable.]

## Markers

- `[SME VERIFY — failure mode]` — borderline adversary output, counsel call.
- `[CITE NEEDED — [authority]]` — adversary referenced a rule or doctrine without specifying section / case.
- `[EVIDENCE FLAG — severity]` — Stage 2 surfaced; verify against the source document.
```

## What this skill does not do

- Predict the outcome. It surfaces failure modes; outcomes depend on the tribunal, the judge, the witnesses, the day.
- Take the case for you. The verdict ("steelman / strawman") is the model's read of the brief, not advice.
- Replace counsel's strategic call. Settle, withdraw, strengthen — all counsel decisions.
- Cover non-UK procedure (US federal, Scotland, NI).
- Run real-time during trial. This is pre-action, pre-settlement, or pre-funding use.
- Replace formal counsel opinion. A KC's view on a case strength matters more than this output. Pre-Motion is a structured prompt for that conversation, not a substitute.

## v0.2 roadmap

A separate `settlement-helper` skill ships in v0.2 covering Calderbank / Part 36 mechanics, BATNA / ZOPA / Nash bargaining analysis — the things originally scoped into Pre-Motion that belong in their own surface.
