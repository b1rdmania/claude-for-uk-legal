---
name: settlement-agreement-review
description: Reviews or drafts a settlement agreement under s.203 ERA 1996 for England & Wales. Validates the statutory conditions (writing, specific complaints, independent adviser, identification, insurance, statement of conditions), drafts the substantive terms (sum, tax characterisation, confidentiality, references, restrictive covenants, indemnities), and surfaces enforceability risks. Use when the user says "review this settlement agreement", "draft a settlement agreement", "compromise agreement" (old term), or asks whether an agreement is binding.
argument-hint: "[--mode=review|draft] [--party=employer|employee]"
---

# /settlement-agreement-review

1. Test statutory validity under s.203 ERA 1996. An agreement that does not meet the conditions does not contract out of statutory rights and the employee can still claim.
2. Review the substantive terms against the party's position (employer or employee).
3. Surface tax issues (ITEPA 2003 — termination payments, PENP).
4. Output a marked-up version with comments or a clean draft.

---

# Settlement agreement (s.203 ERA 1996)

## Purpose

A settlement agreement is the standard vehicle for compromising employment claims. It must comply with the conditions in s.203 ERA 1996 (and equivalent provisions in other statutes — EqA 2010 s.144, TULR(C)A 1992 s.288, etc.) to validly settle the statutory claims it purports to cover. Otherwise the employee remains free to bring a claim.

The other valid vehicle is an ACAS COT3 (recorded by the ACAS conciliator) — no s.203 conditions apply. COT3s are simpler; settlement agreements allow more bespoke terms.

## s.203 statutory conditions (cumulative — all must be satisfied)

1. **In writing.**
2. **Relates to the particular complaint** — generic "all claims" wording without identifying the claims is not enough. List each statutory cause of action by name and section.
3. **Independent adviser** — the employee must have received advice from a "relevant independent adviser" (qualified lawyer, certified trade union official, certified advice centre worker, or other prescribed adviser).
4. **Adviser identified** — name and address in the agreement.
5. **Adviser insured** — a contract of insurance or indemnity provided by a professional body covering the adviser against the risk of loss arising from the advice.
6. **Statement that the conditions are satisfied** — express recital.

A missing condition is fatal. The agreement may still settle contract claims (which don't need s.203 compliance) but won't bar statutory ET claims.

## Substantive terms — checklist

### Payment

- **Sum** — total compensation payment.
- **Breakdown by head**:
  - Statutory redundancy (s.135 ERA — tax-free up to £30k, doesn't count to PENP).
  - Notice / PILON — taxable as earnings (s.402B ITEPA — PENP regime).
  - Ex-gratia compensation for loss of office — first £30k tax-free under s.401-403 ITEPA, balance taxable as employment income.
  - Restrictive covenant payment — taxable as earnings (s.225 ITEPA — restrictive undertakings).
  - Injury to feelings (discrimination cases) — typically tax-free if causally linked to the discrimination rather than termination (Moorthy litigation; HMRC position contested — `[SME VERIFY — current HMRC view]`).
  - Pension contribution.
  - Legal fees contribution (typically £500-£750 plus VAT, paid direct to the adviser).
- **Tax indemnity** — employee indemnifies employer against any further income tax / NICs claimed by HMRC on the termination payment. Standard for employer; employee should resist a broad indemnity that catches tax the employer should have deducted.
- **Payment date** — typically within 14-28 days of the termination date / signature.

### Confidentiality and non-disparagement

- Mutual non-disparagement preferred from employee's side.
- Confidentiality — usually two-way; carve-outs for spouse/partner, professional advisers, regulators (whistleblowing — must not gag protected disclosures, see s.43J ERA), HMRC, and court orders. Recent law has tightened on NDAs in discrimination/harassment cases — `[SME VERIFY — Victims and Prisoners Act 2024 NDA restrictions in regulated professions]`.

### Reference

- Agreed wording attached as a schedule.
- "Factual reference only" is a common employer position. Employee should push for a positive agreed reference.
- Obligation on employer to give substantially the same reference to any future enquirer for [X years / indefinitely].

### Warranties and reps

- Employee typically warrants no other unresolved complaints and no knowledge of any matter that would give rise to a complaint.
- Employee returns property, deletes data.
- Employee waives reinstatement / re-engagement.

### Restrictive covenants

- Either confirm existing covenants remain in force (employer position), or release them (employee position).
- Garden leave already served counts against post-termination restraint enforceability.

### Claims covered

- List each statutory claim by name. Generic "all claims" tail is acceptable as a backstop but does not save a missing specific complaint.
- Carve-outs (standard): accrued pension rights, personal injury (latent / unknown), enforcement of the agreement itself.

### Governing law / jurisdiction

- Laws of England and Wales. Exclusive jurisdiction of E&W courts (with ET retained jurisdiction over the underlying employment claims pending settlement).

## Workflow

### Step 1 — Statutory validity

Run through the s.203 checklist. Flag any condition missing or doubtful.

### Step 2 — Substantive review

Walk through each substantive term against the checklist. Flag terms that are unusual, missing, or commercially adverse to the user's side.

### Step 3 — Tax review

Validate the breakdown. Recompute PENP if PILON is being paid (PENP formula: (BP × D) / P — where BP = basic pay in pay period before notice, D = days in unworked notice, P = days in pay period).

### Step 4 — Mark up

Output either: (a) commented review with risk flags, or (b) clean draft.

## Output template (review mode)

# Settlement Agreement Review — [Employee] / [Employer]

## Statutory validity (s.203 ERA / s.144 EqA)

| Condition | Status | Note |
|---|---|---|
| In writing | ✓/✗ | |
| Specific complaints identified | ✓/✗/Partial | Missing: [...] |
| Independent adviser | ✓/✗ | |
| Adviser named and addressed | ✓/✗ | |
| Adviser insured (recital) | ✓/✗ | |
| s.203 conditions satisfied (recital) | ✓/✗ | |

**Overall: [Valid / Invalid — fix items above]**

## Substantive review

| Clause | Position | Risk to [user side] | Suggested change |
|---|---|---|---|
| Payment breakdown | [...] | [tax / quantum] | [...] |
| Confidentiality | [...] | [over-broad / under-broad] | [...] |
| Reference | [...] | | |
| Warranties | [...] | | |
| Restrictive covenants | [...] | | |
| Claims schedule | [...] | | |
| Tax indemnity | [...] | | |

## Tax analysis

- PILON / PENP: £[X] taxable as earnings.
- s.401-403 ITEPA: first £30k tax-free, balance £[Y] taxable.
- [Other heads.]
- Effective net to employee: £[Z].

## Recommended changes

[Numbered list of specific edits, in priority order.]

## Markers

- `[NOT s.203 COMPLIANT — agreement does not validly settle statutory claims]`
- `[SME VERIFY — HMRC current view on injury-to-feelings tax]`
- `[SME VERIFY — Victims and Prisoners Act 2024 NDA restrictions]`
- `[SME VERIFY — PENP figures]`

## What this skill does not do

- Provide independent legal advice to the employee — that must come from a qualified adviser per s.203(3A).
- Compute tax to the penny — final figures need accountant / tax counsel sign-off in non-trivial cases.
- Cover Scotland / NI (different statutory framing).
