---
name: unfair-dismissal-screener
description: Screens a proposed dismissal or an alleged unfair dismissal against the s.94 ERA framework for England & Wales. Tests qualifying service, identifies automatically unfair categories (no qualifying period), applies the Burchell, Polkey, and band-of-reasonable-responses tests, and surfaces specific procedural risks. Use when the user says "is this unfair", "screen this dismissal", "ordinary unfair dismissal", "automatic unfair dismissal", or wants a fairness assessment before or after dismissal.
argument-hint: "[--mode=pre-dismissal|post-dismissal]"
---

# /unfair-dismissal-screener

1. Qualifying service test (s.108 ERA): two years continuous service, **unless** the dismissal falls within an automatically unfair category (no qualifying period required).
2. Identify the potentially fair reason advanced (s.98(2)): conduct, capability, redundancy, illegality, some other substantial reason. If none, s.98(1) — burden on employer to show fair reason.
3. Apply the Burchell test (conduct cases): reasonable belief, reasonable investigation, dismissal within the band of reasonable responses.
4. Apply Polkey (procedural fairness): if the dismissal was procedurally unfair, what was the chance it would have happened anyway? Reduces compensatory award.
5. Apply ACAS Code: failure to follow can produce up to 25% uplift (s.207A TULR(C)A 1992).
6. Output a risk score with the reasoning visible.

---

# Unfair dismissal screener

## Purpose

Quick, structured fairness assessment. Pre-dismissal: helps an employer decide whether to proceed. Post-dismissal: helps either side assess the strength of a prospective claim.

## Qualifying service gate (s.108 ERA 1996)

Default rule: ordinary unfair dismissal requires **two years' continuous service** (effective from 6 April 2012 for employees who started on or after that date).

**No qualifying period applies if** the dismissal is automatically unfair, including (non-exhaustive):

| Category | Statute |
|---|---|
| Whistleblowing — disclosure under s.43B ERA | s.103A ERA |
| Trade union membership or activities | s.152 TULR(C)A 1992 |
| Pregnancy, maternity, parental leave | s.99 ERA |
| Health and safety — designated representative, raising concern | s.100 ERA |
| Asserting a statutory right | s.104 ERA |
| Working Time Regulations | s.101A ERA |
| National Minimum Wage | s.104A ERA |
| TUPE — for ETO reason or in connection with transfer | reg 7 TUPE 2006 |
| Family-friendly rights (paternity, adoption, flexible working request, etc.) | various ERA sections |
| Spent convictions | s.4(3)(b) Rehabilitation of Offenders Act 1974 |
| Jury service | s.98B ERA |
| Discriminatory dismissal | EqA 2010 (which is a separate cause of action — but the dismissal is also "automatically unfair" in effect — plead both) |

Plus the Labour government's 2024–25 Employment Rights Bill is expected to introduce day-one unfair dismissal rights subject to a statutory probation period. `[SME VERIFY — Employment Rights Act 2025 implementation date and probationary regime]`.

## Potentially fair reasons (s.98(2) ERA)

1. Conduct
2. Capability or qualifications
3. Redundancy (specific s.139 definition)
4. Illegality (continued employment would contravene a statutory restriction)
5. Some other substantial reason (SOSR) — catch-all for genuine business reasons not in the first four

The employer must show **the reason** (s.98(1)). The Tribunal then decides whether the dismissal was fair "having regard to the reason shown" (s.98(4)).

## Burchell test (conduct dismissals — British Home Stores v Burchell)

Three limbs:

1. The employer must have a **genuine belief** in the employee's misconduct.
2. The belief must be based on **reasonable grounds**.
3. The employer must have carried out a **reasonable investigation**.

Each limb is assessed by reference to the band of reasonable responses test (Iceland Frozen Foods v Jones — would a reasonable employer in those circumstances have come to that conclusion?). The Tribunal does not substitute its own view.

## Polkey (procedural fairness — Polkey v A.E. Dayton Services)

A dismissal that was substantively justifiable but procedurally unfair is **unfair**, but the compensatory award is reduced by the percentage chance that the employee would have been dismissed in any event had a fair procedure been followed (the "Polkey reduction").

A 100% Polkey reduction (no compensation but still a finding of unfair dismissal) is possible.

## ACAS Code uplift

Failure to follow the ACAS Code of Practice on Disciplinary and Grievance Procedures — applies to conduct and performance dismissals, not redundancy / SOSR — can result in up to **25% uplift** on compensation (s.207A TULR(C)A 1992). Conversely, an employee's unreasonable failure to follow the Code can result in a 25% reduction.

## Workflow

### Step 1 — Eligibility

Qualifying service: yes / no. If no, is there an automatically unfair head? If neither, ordinary unfair dismissal claim is unavailable. Test for discrimination (EqA 2010) which has no qualifying period.

### Step 2 — Reason

What reason does the employer say? Is it within s.98(2)? Note: pretextual reasons fail at this stage — burden on employer.

### Step 3 — Fairness

Apply the relevant framework (Burchell for conduct, capability cases follow a similar pattern with warnings + improvement opportunity; redundancy has its own framework — pool, selection criteria, consultation, suitable alternative employment per Williams v Compair Maxam).

### Step 4 — Procedure

ACAS Code compliance. Investigation, invitation, hearing, right to be accompanied (s.10 Employment Relations Act 1999), decision, right of appeal. Each is a discrete procedural step; failure of any is a procedural defect.

### Step 5 — Polkey + ACAS adjustments

Estimate Polkey % and ACAS uplift. Multiply through to a risk-adjusted compensation range.

### Step 6 — Output

Structured risk score with the reasoning.

## Output template

# Unfair Dismissal Screen — [Employee name]

## Eligibility

- Start date: [YYYY-MM-DD]
- EDT: [YYYY-MM-DD]
- Continuous service: [X years Y months]
- **Qualifies for ordinary unfair dismissal (s.94 ERA):** [yes/no]
- Automatic unfair heads in play: [list, with statute]
- EqA discrimination overlay: [yes/no — protected characteristic]

## Reason advanced by employer

- Reason: [conduct / capability / redundancy / illegality / SOSR]
- Stated basis: [...]
- Is the reason genuine? [...]

## Fairness analysis

### Substantive (Burchell for conduct):
- Genuine belief: [...]
- Reasonable grounds: [...]
- Reasonable investigation: [...]
- Within band of reasonable responses: [...]

### Procedural (ACAS Code):
- Investigation: [...]
- Written notice of allegation: [...]
- Hearing with right to be accompanied: [...]
- Decision in writing: [...]
- Right of appeal: [...]

## Risk score

| Factor | Position | Weight |
|---|---|---|
| Substantive fairness | Strong / Borderline / Weak | |
| Procedural fairness | Strong / Borderline / Weak | |
| Polkey reduction estimate | [%] | |
| ACAS uplift estimate | [%] | |

**Overall risk to employer: [Low / Medium / High]**

## Compensation range (if claim succeeds)

- Basic award (s.119 ERA): £[X]
- Compensatory award (s.123 ERA, capped per s.124): £[Y] — range reflecting Polkey
- ACAS uplift: + [up to 25%]
- Range: £[low] – £[high]

## Recommended actions

- [Pre-dismissal: fix specific procedural defects before proceeding.]
- [Post-dismissal: settlement window / appeal outcome / ET1 strategy.]

## Markers
- `[SME VERIFY — current statutory cap, week's pay, ERB 2025 status]`

## What this skill does not do

- Decide. The screen is a structured aid. Counsel calls the strategic shot.
- Quantify pension loss precisely.
- Cover redundancy selection-criteria challenges in detail (separate skill territory).
- Cover Scotland / NI.
