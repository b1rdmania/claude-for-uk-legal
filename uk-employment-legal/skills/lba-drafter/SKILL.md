---
name: lba-drafter
description: Drafts a Letter Before Action (LBA) for an employment dispute in England & Wales. Use when the user needs to put an employer on notice of a prospective Employment Tribunal claim or High Court / County Court claim arising from the employment relationship, before issuing proceedings. Triggers include "draft an LBA", "letter before action for unfair dismissal", "letter before claim", "put the employer on notice", or "pre-action letter".
argument-hint: "[claim-type] [--respondent=name]"
---

# /lba-drafter

1. Confirm jurisdiction is England & Wales. Scotland and Northern Ireland have different time limits, tribunals, and procedural rules — this skill does not cover them.
2. Identify the dispute type: Employment Tribunal claim (unfair dismissal, discrimination, unlawful deduction, etc.) or contractual / High Court / County Court claim (wrongful dismissal, breach of contract, unpaid bonus over £25k).
3. Gather: claimant details, respondent details, factual chronology, statutory or contractual basis, remedies sought, deadline for response.
4. Apply the correct pre-action framework — Pre-Action Conduct Practice Direction for civil claims; ACAS Code of Practice for ET claims.
5. Draft. Surface time-limit risks before output (see Time-limit gate).
6. Output the letter with a header noting whether ACAS early conciliation has started and the relevant primary limitation date.

---

# Letter Before Action — UK employment

## Purpose

The LBA puts the prospective respondent on notice, sets out the claimant's case, invites response or settlement, and (where applicable) complies with pre-action protocols. A well-drafted LBA narrows issues, opens settlement, and protects costs position if the matter proceeds.

For Employment Tribunal claims, there is no formal pre-action protocol equivalent to those in civil litigation. The ACAS Code of Practice on Disciplinary and Grievance Procedures governs conduct that may affect compensation (up to 25% adjustment under s.207A TULR(C)A 1992). The LBA is still useful as a settlement and narrowing device.

For contractual employment claims in the civil courts, the Pre-Action Conduct Practice Direction applies, and non-compliance can attract costs sanctions.

## Time-limit gate (unbypassable)

Before drafting, surface the limitation position. Employment Tribunal claims have **three-month** primary time limits (one month for some redundancy and TUPE claims) running from the act complained of (e.g. effective date of termination, last act of discrimination). ACAS early conciliation under s.18A Employment Tribunals Act 1996 extends the limit via the "stop the clock" mechanism in s.207B ERA 1996 — and the LBA does NOT stop time.

Infer from the matter file or inputs. Surface for confirmation only if not provided:
- The act complained of and its date.
- Whether ACAS early conciliation has been started; if yes, Day A (notification to ACAS) and Day B (EC certificate issued).

Compute the latest date for issuing the ET1 and flag it in the letter header. If the primary limitation is less than 14 days away, recommend issuing ACAS notification before sending the LBA — do not let a polite pre-action letter cost the client their claim. Flag inline: `[TIME LIMIT — ET1 must issue by [date]]`.

## Inputs to gather

- Claimant: full name, NI number (optional), address, dates of employment, role, contract type (employee / worker / self-employed — affects rights available).
- Respondent: legal entity name (check Companies House for limited companies, not the trading name), registered address, additional respondents if the claim is against named individuals for discrimination or harassment.
- Facts: chronology with dates. Pin down the effective date of termination if dismissal is alleged.
- Heads of claim: statutory (e.g., s.94 ERA — unfair dismissal; ss.13-27 ERA — unlawful deductions; Equality Act 2010 protected characteristics) or contractual.
- Remedies sought: reinstatement, re-engagement, basic and compensatory award, injury to feelings (discrimination), interest, costs (note ET costs regime is restrictive — see ETR 2013 rule 76).
- Settlement appetite: is the LBA inviting settlement, or purely putting on notice?

## Workflow

### Step 1 — Confirm jurisdiction and capacity

England & Wales only. Confirm the claimant was working under English law (Lawson v Serco-style territorial scope checks for unusual cases). Confirm the respondent is a legal entity that can be served.

### Step 2 — Confirm claim type and forum

Most employment claims go to the Employment Tribunal. Contractual claims for sums over £25,000 must go to the civil courts (ET jurisdiction over contract claims under the Employment Tribunals (Extension of Jurisdiction) Order 1994 is capped at £25,000 and only on termination). Discrimination claims always go to the ET. Wrongful dismissal can go to either.

### Step 3 — Apply the correct pre-action framework

- **ET claim**: ACAS Code of Practice on Disciplinary and Grievance Procedures, plus the ACAS early conciliation regime (s.18A ETA 1996).
- **Civil claim**: Pre-Action Conduct PD, plus any specific protocol (none applies to most employment-contract claims, so PACC alone).

### Step 4 — Draft

Use the structure in the output template. Keep tone firm but not aggressive. Plead the cause of action, the facts that support each element, and the loss. Invite a substantive response within a reasonable deadline (14 days for civil PACC by default; 14-21 days is conventional for ET LBAs).

### Step 5 — Costs and "without prejudice"

The LBA itself is open correspondence. If a settlement offer is being made, mark a separate enclosure "Without Prejudice Save As To Costs" — do not mix open and WP material in one letter. See the `without-prejudice-drafter` skill for WP correspondence.

## Output template

[Solicitor letterhead / client letterhead]

[Date]

[Respondent name]
[Respondent address]

**BY EMAIL AND POST**

Dear Sirs,

**Re: [Claimant name] — Letter Before Action**

We act for [Claimant], formerly employed by you as [role] from [start date] to [EDT or date of resignation].

**Time-limit notice:** The primary limitation period for an Employment Tribunal claim arising from these matters expires on [date]. ACAS early conciliation [has been started on [date] / will be commenced shortly]. This letter does not extend the limitation period.

## 1. Background facts

[Numbered chronology of material facts, dated, neutral in tone.]

## 2. Cause(s) of action

[For each head of claim, plead the statutory or contractual basis and apply the facts to the elements.]

- **Unfair dismissal (s.94 ERA 1996)**: Our client had [length] of continuous service and was dismissed on [date]. The dismissal was unfair because [Burchell / Polkey / band of reasonable responses analysis]. Reason: [conduct / capability / redundancy / SOSR / automatically unfair].
- **Discrimination (Equality Act 2010, s.[13/19/26/27])**: Protected characteristic — [characteristic]. Less favourable treatment / PCP / unwanted conduct / detriment. Comparator (actual or hypothetical): [...].
- **Unlawful deduction from wages (s.13 ERA 1996)**: Sums properly payable but not paid: [amount and basis].
- **Wrongful dismissal / breach of contract**: Notice period [length]; pay in lieu owed: [amount].

## 3. Loss and remedy sought

[Basic award computation; compensatory award (capped at lower of one year's pay or statutory cap, currently £115,115 for dismissals on or after 6 April 2025 — verify current cap); injury to feelings per Vento bands; interest; pension loss.]

We invite you to make proposals for settlement within [14 / 21] days of the date of this letter, failing which our client reserves the right to issue proceedings without further notice.

Please confirm by return whether you instruct solicitors and, if so, provide their contact details for service.

## 4. ACAS Code

Our client expects you to engage with the ACAS Code of Practice. Failure to do so may result in an uplift of up to 25% on any compensation award under s.207A TULR(C)A 1992.

## 5. Costs

In the Employment Tribunal, costs are awarded only in limited circumstances (ETR 2013 rule 76). In any civil proceedings, our client will rely on this letter on the question of costs under CPR Part 44.

Yours faithfully,

[Signature block]

## Markers used

- `[TIME LIMIT — ET1 must issue by [date]]` — when limitation is close.
- `[SME VERIFY — current statutory cap]` — for figures that change annually (compensatory award cap, statutory week's pay, Vento bands).
- `[FACT NEEDED — [what's missing]]` — for gaps that must be filled before sending.

## What this skill does not do

- Send the letter. Solicitor signs and serves.
- Compute ACAS EC time extensions precisely (use a date calculator and verify against s.207B ERA 1996).
- Advise on without-prejudice settlement strategy in the same document — that's the `without-prejudice-drafter` skill.
- Cover Scotland or Northern Ireland.
- Replace independent legal advice for the claimant.
