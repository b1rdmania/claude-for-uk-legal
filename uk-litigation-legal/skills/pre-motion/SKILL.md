---
name: pre-motion
description: Runs a settlement analysis on a UK civil dispute using a Nash bargaining frame. Maps each side's BATNA (best alternative to a negotiated agreement), expected litigation cost-and-outcome, and risk tolerance to identify the zone of possible agreement, the Nash bargaining solution, and the optimal Part 36 / Calderbank strategy. Use when the user says "pre-motion", "settle this", "Nash analysis", "what should I offer", "zone of possible agreement", or wants a structured view on whether and how to settle.
argument-hint: "[--mode=claimant|defendant|joint]"
---

# /pre-motion

1. Elicit each side's inputs: claim value, expected costs to trial, probability of success on the merits, risk tolerance (utility curve), strategic preferences (precedent, reputation, deterrence).
2. Compute BATNA for each side — the expected value of going to trial.
3. Identify the ZOPA (zone of possible agreement) — the overlap between each side's reservation prices.
4. Compute the Nash bargaining solution — the settlement point that maximises the product of each party's surplus over BATNA.
5. Translate the result into a Part 36 / Calderbank offer recommendation.
6. Output a one-page brief that names assumptions explicitly. The strength of the recommendation is bounded by the strength of the inputs — surface that.

---

# Pre-motion: structured settlement analysis

## Purpose

Most cases settle. The question is at what number and on what terms. A structured analysis turns gut-feel negotiation into a defensible model that:

- Tests whether the case should settle at all (sometimes BATNAs don't overlap and trial is rational).
- Identifies the range within which both sides should be willing to settle.
- Suggests a focal point (the Nash solution).
- Times offers around CPR Part 36 to maximise costs pressure.

This is not a substitute for judgment. It is a structured way to challenge it.

## Inputs

For each side, gather:

| Input | Notes |
|---|---|
| Claim value (V) | Quantum if claimant wins on all heads. Best-case for claimant. |
| Probability of success on liability (Pl) | 0–1 |
| Probability of success on quantum given liability (Pq) | 0–1, often distinct from liability |
| Discounted recovery (R) | V × Pl × Pq — expected recovery at trial before costs |
| Costs to trial (C) | Own-side legal spend through trial |
| Costs at risk (Crisk) | Other-side costs they would pay if they lose (CPR 44 standard or indemnity) |
| Time to trial (T) | Months — affects discounting and management cost |
| Risk tolerance (ρ) | Subjective: 0 = risk-neutral, 1 = highly risk-averse. Drives the discount on the gamble. |
| Strategic value (S) | Precedent, reputation, deterrence, regulator signal — qualitative, surfaced not quantified |

## BATNA computation

### Claimant BATNA
`BATNA_C = (V × Pl × Pq) − C_C + (Pl × Pq) × C_D − (1 − Pl × Pq) × C_D_atrisk − ρ_C × σ`

Plain English:
- Claimant expects to recover V × Pl × Pq.
- Less own costs C_C.
- Plus, if they win, recovery of defendant's costs (assumed standard-basis recovery — discount by recoverability factor, often 60-70% of incurred costs).
- Less, if they lose, defendant's costs paid out.
- Less a risk-aversion premium ρ × σ, where σ is the standard deviation of the outcome.

### Defendant BATNA
`BATNA_D = − (V × Pl × Pq) − C_D + (1 − Pl × Pq) × C_C_recovery − (Pl × Pq) × C_C − ρ_D × σ`

(Negative — defendant expects to pay.)

### Reservation prices

- **Claimant's reservation price** = lowest settlement they should accept = BATNA_C (in cash today, no discount).
- **Defendant's reservation price** = highest settlement they should pay = −BATNA_D.

ZOPA exists if claimant's reservation ≤ defendant's reservation.

## Nash bargaining solution

Where ZOPA exists, the Nash solution is the settlement S that maximises:

`(S − BATNA_C) × (−BATNA_D − S)`

Differentiate, set to zero:

`S_Nash = (BATNA_C + (−BATNA_D)) / 2`

i.e. the midpoint of the ZOPA. This is the symmetric Nash solution. Asymmetric weights (relative bargaining power, urgency, asymmetric information) shift the solution toward the stronger party.

## Strategic overlay

Pure expected-value analysis ignores three things that matter:

1. **Precedent / reputation.** A defendant who settles every weak claim invites more. A claimant who never settles teaches respondents not to negotiate. Adjust the implied future cost.
2. **Information asymmetry.** A confident party may signal by going low (Part 36) and forcing the other side to read confidence. The signal value is part of the offer's price.
3. **Time and management cost.** Litigation costs more than the legal spend — management time, distraction, document burden. Larger for SMEs than for institutional litigants.

## Part 36 / Calderbank timing

Once Nash is computed, translate into a costs-protected offer:

- **Claimant offer to settle** at a number ≤ Nash + a margin. If beaten at trial, claimant gets enhanced interest, indemnity costs from end of relevant period, and the s.36.17 additional amount.
- **Defendant offer to settle** at a number ≥ Nash − a margin. If claimant fails to beat it at trial, defendant gets costs from end of relevant period.

Time the offer to expire just before a key cost event (witness statements, expert reports, trial bundle) to maximise the perceived cost of refusal.

In the **Employment Tribunal**, Part 36 does not apply. Use ACAS COT3 (if ACAS is involved) or Calderbank — but expect weaker costs consequences under ETR 2013 rule 76. See `part-36-offer` skill.

## Workflow

### Step 1 — Elicit inputs
Walk through the table. Where the user does not know an input, give a default range and flag the sensitivity.

### Step 2 — Compute BATNAs
Show working.

### Step 3 — Test for ZOPA
If none, surface honestly. Recommend trial preparation, not settlement.

### Step 4 — Compute Nash
Symmetric first. Then asymmetric overlay if bargaining power is uneven.

### Step 5 — Sensitivity
Vary the most uncertain input (usually Pl) by ±20%. Show how the Nash moves. The recommendation is only as strong as the inputs.

### Step 6 — Translate to offer
Specific number, vehicle, timing, deadline.

## Output template

# Pre-motion settlement analysis — [Case ref]

## Assumptions

| Parameter | Claimant view | Defendant view | Used in model | Confidence |
|---|---|---|---|---|
| Claim value | £[X] | £[X'] | £[mid] | H/M/L |
| P(liability) | [%] | [%] | [%] | |
| P(quantum) | [%] | [%] | [%] | |
| Costs to trial (C) | £[...] | £[...] | | |
| Time to trial | [months] | | | |

## BATNAs

- Claimant BATNA: £[X]
- Defendant BATNA: −£[Y]

## ZOPA

[Yes / No]. Range: £[low] – £[high].

## Nash solution

**£[N]** (midpoint of ZOPA).

Sensitivity:
- P(liability) +20%: Nash → £[N']
- P(liability) −20%: Nash → £[N'']
- Costs +50%: Nash → £[N''']

## Recommended offer

[Claimant side: open settlement discussions at £[high end], real Part 36 at £[Nash + margin], deadline aligned to [event].]

[Defendant side: open at £[low end], real Part 36 at £[Nash − margin] timed to expire before [event].]

## Strategic flags

- [Precedent / reputational considerations.]
- [Information asymmetry.]
- [Time cost.]

## Markers
- `[ASSUMPTION — verify P(liability) — biggest sensitivity]`
- `[SME VERIFY — costs recovery percentage under CPR 44]`

## What this skill does not do

- Replace counsel's judgment on prospects. The probabilities are inputs, not outputs.
- Run a real Monte Carlo (it computes deterministic ZOPA + sensitivity, which is usually enough).
- Apply in the Employment Tribunal where Part 36 doesn't run — see `part-36-offer` for ET-specific vehicles.
- Handle multi-party settlements with complex contribution dynamics (handle bilaterally; flag contribution claims separately).
