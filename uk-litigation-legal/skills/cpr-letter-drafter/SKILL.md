---
name: cpr-letter-drafter
description: Drafts a Letter Before Claim (England & Wales) compliant with the Practice Direction on Pre-Action Conduct and Protocols, or with a sector-specific pre-action protocol where one applies (debt, professional negligence, housing disrepair, personal injury, etc.). Use when the user says "draft an LBC", "letter before claim", "pre-action letter", "pre-action protocol", or needs to start the pre-action clock before issuing a civil claim.
argument-hint: "[--protocol=auto|pacc|debt|prof-neg|disrepair|pi|other]"
---

# /cpr-letter-drafter

1. Identify whether a specific pre-action protocol applies (debt, professional negligence, housing disrepair, personal injury, construction, judicial review, etc.) or whether the default Practice Direction — Pre-Action Conduct and Protocols (PACC) applies.
2. Apply the relevant timing, content, and disclosure requirements.
3. Draft the LBC with the structure that protocol expects.
4. Surface costs and CPR Part 36 consequences if the matter proceeds.

---

# Letter Before Claim (England & Wales civil)

## Purpose

The pre-action regime narrows issues, encourages settlement, and exposes parties who don't engage to costs sanctions. Non-compliance with PACC or a specific protocol can result in:

- Stay of proceedings until compliance.
- Adverse costs orders (CPR 44).
- Lost interest entitlement.
- Adverse inferences on conduct under CPR 44.2.

## Choosing the framework

| Claim type | Protocol |
|---|---|
| Debt claim where debtor is an individual (incl. sole trader) | Pre-Action Protocol for Debt Claims (Oct 2017) |
| Professional negligence (solicitors, accountants, surveyors, etc.) | Pre-Action Protocol for Professional Negligence |
| Personal injury (≤ £25k portal; > £25k or non-portal) | Pre-Action Protocol for Personal Injury Claims |
| Housing disrepair | Pre-Action Protocol for Housing Disrepair Claims |
| Construction & Engineering | Pre-Action Protocol for Construction and Engineering Disputes |
| Judicial review | Pre-Action Protocol for Judicial Review |
| Defamation | Pre-Action Protocol for Defamation |
| Possession claims | Pre-Action Protocol for Possession Claims by Social Landlords (where applicable) |
| Anything else | Practice Direction on Pre-Action Conduct and Protocols (PACC) — default |

## PACC core requirements (default)

- Concise summary of the claim.
- Basis on which the claim is made.
- Summary of facts.
- What the claimant wants.
- If money: how it is calculated.
- Reasonable period for response (typically 14 days for a simple claim, up to 3 months for a complex one).
- Documents the claimant relies on.
- An indication of an intention to use ADR if response is inadequate.

## Debt Claims Protocol specifics

- Information sheet and reply form must accompany the letter.
- 30 days for the debtor to respond (longer than PACC default).
- Debtor's response form options: I dispute / I admit / I admit in part / I need time / I want ADR.
- Statement of account (if interest or charges added) must be provided.
- Cannot start proceedings until 30 days after the LBC (or longer if debtor reasonably needs time).

## Professional Negligence Protocol specifics

- Preliminary notice (no detailed allegations) first. Recipient acknowledges within 21 days.
- Then Letter of Claim with detailed allegations.
- 3 months for the Letter of Response.
- Encourages mutual disclosure and joint experts.

## Inputs

- Parties (claimant, defendant — Companies House for limited companies; trading name is not enough).
- Cause of action (contract, tort, statutory).
- Facts (chronology).
- Loss / remedy (with breakdown).
- Documents to disclose with the LBC.
- Whether ADR is proposed.
- Time pressure (limitation looming?).

## Limitation gate

Most contract and tort claims: 6 years (Limitation Act 1980 s.5, s.2). Personal injury: 3 years (s.11). Latent damage: special rules (s.14A — 3 years from knowledge / 15-year long-stop). Judicial review: promptly and in any event within 3 months (CPR 54.5). Defamation: 1 year (s.4A). 

The LBC does **not** stop limitation. If limitation is near, issue protectively and consider a stay for pre-action compliance.

Surface inline: `[LIMITATION — primary limit expires [date]; consider protective issue]`.

## Workflow

### Step 1 — Identify protocol
From the claim type. If unclear, default to PACC.

### Step 2 — Limitation check
Surface the latest issue date.

### Step 3 — Draft per protocol
Use the relevant template.

### Step 4 — Disclosure with LBC
Identify documents to enclose. Limited disclosure at LBC stage; full disclosure later.

### Step 5 — ADR signal
PACC and most protocols require parties to consider ADR. Stating willingness in the LBC is standard. Refusal to engage in ADR can be costs-penalised (Halsey v Milton Keynes NHS Trust [2004]; further calibrated in Churchill v Merthyr Tydfil [2023] — court may order ADR).

## Output template (PACC default)

[Solicitor letterhead]

[Date]

[Defendant name]
[Address]

**BY EMAIL AND POST**

Dear Sirs,

**Re: [Claimant name] — Letter Before Claim**

We act for [Claimant]. We are writing in accordance with the Practice Direction — Pre-Action Conduct and Protocols [or the relevant protocol].

**Limitation notice:** The primary limitation period for the claim described below expires on [date].

## 1. The parties

[Claimant — full legal name, address. Defendant — full legal name, registered office (for companies).]

## 2. Facts

[Numbered chronology of material facts.]

## 3. The claim

[For each cause of action — contract, tort, statutory — state the basis and apply the facts to the elements.]

- **Breach of contract:** The contract was [terms / when formed]. The Defendant breached clause [X] by [act / omission]. The breach caused the loss particularised below.
- **Negligence:** The Defendant owed our client a duty of care because [...]. It breached that duty by [...]. The breach caused [...].
- **Statutory:** [Cite the statute and section, plead the elements, apply the facts.]

## 4. Loss and damage

[Particularised loss with computation.]

- Head 1: [...] £[X]
- Head 2: [...] £[Y]
- Interest under s.35A Senior Courts Act 1981 / s.69 County Courts Act 1984 (or contractual rate if applicable).

**Total: £[Z]**

## 5. Documents

Enclosed:
- [Documents the claimant relies on.]

Please provide:
- [Documents requested from the defendant.]

## 6. ADR

Our client is willing to consider ADR (including mediation). Please indicate within your response whether your client is willing to engage and, if so, your preferred form and timing.

## 7. Response

Please provide a Letter of Response within [21 days / per protocol]. The response should:
- Accept or deny the claim.
- State the facts and matters relied on.
- Identify documents relied on.
- Address the proposal on ADR.

## 8. Costs

If proceedings are issued and our client succeeds, costs will be sought under CPR Part 44. Our client reserves the right to make a CPR Part 36 offer at any stage.

Yours faithfully,

[Signature]

## Markers

- `[LIMITATION — issue by [date]]`
- `[PROTOCOL — [name] applies; consider preliminary notice / 30-day debt window / 3-month prof-neg response]`
- `[SME VERIFY — protocol amendments]`

## What this skill does not do

- Issue the claim. The LBC is pre-action.
- Apply Scottish / NI procedure.
- Replace counsel's call on whether to issue protectively where limitation is tight.
