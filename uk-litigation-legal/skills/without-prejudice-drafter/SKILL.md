---
name: without-prejudice-drafter
description: Drafts correspondence on the correct privilege footing — without prejudice (WP), without prejudice save as to costs (WPSATC / Calderbank), or open. Distinguishes the three, applies them correctly, and surfaces the exceptions to WP protection that frequently catch parties out (Unilever v Procter & Gamble exceptions). Use when the user asks to draft a WP letter, a Calderbank, a settlement letter, or wants to know whether material is protected from disclosure.
argument-hint: "[--type=wp|wpsatc|open]"
---

# /without-prejudice-drafter

1. Identify the correct footing: open, WP, or WPSATC.
2. Apply the right header convention. WP is not protected just because labelled — the substance must be a genuine settlement attempt in an existing or contemplated dispute.
3. Surface the Unilever exceptions: WP protection is not absolute.
4. Draft accordingly. Keep open and WP material in separate documents.

---

# Without prejudice / WPSATC correspondence

## The three footings

| Footing | Disclosure at trial | Use |
|---|---|---|
| **Open** | Yes — fully admissible | Statements of case, demands, pre-action letters not yet in negotiation |
| **Without prejudice (WP)** | No — inadmissible to prove liability or quantum | Genuine settlement negotiations |
| **Without prejudice save as to costs (WPSATC) / Calderbank** | Inadmissible on liability/quantum; **admissible on costs** after judgment | Settlement offers where the offeror wants costs protection but cannot use CPR Part 36 (e.g. Employment Tribunal) or wants Calderbank flexibility |

## When WP protection applies

Three conditions:

1. There is an **existing or contemplated dispute**.
2. The communication is **a genuine attempt to settle** that dispute.
3. The parties intended the communication to be confidential.

A letter labelled "without prejudice" that does not satisfy these conditions is not protected. A letter that satisfies them but is not labelled is still protected (the label is evidence of intention; substance prevails — Rush & Tompkins v GLC [1989]).

## The Unilever exceptions (Unilever v Procter & Gamble [2000])

WP protection is not absolute. The court has admitted WP material in evidence where:

1. The WP communications show the agreement was concluded — to prove or rebut existence/terms of the agreement.
2. The communications are evidence of misrepresentation, fraud, or undue influence.
3. The communications give rise to estoppel.
4. Without admission, exclusion would act as a cloak for "unambiguous impropriety" (e.g. perjury, blackmail, threats).
5. To explain delay or apparent acquiescence (relevant to limitation).
6. The communications are relevant to costs (only if WPSATC was the footing).
7. The communications include a tariff or formula relevant to determining a related issue.

A letter discussing a settlement that also makes a threat or admits a crime is exposed under (4). Practical implication: WP is not a magic shield. Don't write anything you'd be embarrassed by if a judge reads it.

## Calderbank / WPSATC specifics

The Calderbank offer (Calderbank v Calderbank [1976]) lets a party put a settlement on the table that the court will see on costs at the end. Mostly displaced by CPR Part 36 in the civil courts, but still alive where:

- The forum doesn't have Part 36 (Employment Tribunal — see `part-36-offer`).
- The offer is on terms Part 36 cannot accommodate (mixed money and non-money relief; offers including a contribution; offers conditional on third-party action).
- The offeror wants to avoid the strictures of Part 36 formality.

Calderbank cost consequences in the civil courts are weaker than Part 36 — the court has discretion under CPR 44.2 and 36.17 does not apply. State the WPSATC footing explicitly; if uncertain, run the offer as a Part 36 instead.

## Drafting rules

1. **Header**: place the words "Without Prejudice" or "Without Prejudice Save As To Costs" prominently at the top of the document, before the salutation.
2. **Don't mix**: do not put open content and WP content in the same document. If both are needed, write two letters, one open, one WP, cross-referenced.
3. **No threats**: don't put anything in a WP letter that you would not want read out in court if WP fails.
4. **Settlement substance**: state clearly that the letter is part of a genuine attempt to settle the [described dispute].
5. **Authority**: a WP offer should be authorised by the client and confirm the lawyer has authority to bind on those terms (or expressly state subject-to-client-approval).
6. **Acceptance mechanics**: how is acceptance communicated; how long is the offer open; what happens if not accepted.
7. **Costs reservation (WPSATC only)**: expressly reserve the right to refer to the letter on costs.

## Workflow

### Step 1 — Confirm footing
Infer the intended footing from the request:
- "Settlement offer" or "without prejudice letter" → WP.
- "Calderbank", "costs protection", "offer with costs consequences", or any ET-context offer → WPSATC.
- "Demand", "letter before claim", "on the record" → open (use `cpr-letter-drafter` instead).
Surface for confirmation only if ambiguous from the request.

### Step 2 — Confirm dispute
Is there an existing or contemplated dispute? If no, WP doesn't apply — use open correspondence.

### Step 3 — Draft

Use the appropriate template. Keep separate from any open correspondence going out the same day.

### Step 4 — Surface exceptions

Flag any content that risks an Unilever exception (admissions, threats, signals of estoppel).

## Output templates

### Without Prejudice

**WITHOUT PREJUDICE**

[Date]

[Recipient]

Dear Sirs,

**Re: [Matter — dispute description]**

This letter is written without prejudice as a genuine attempt to settle the dispute between our respective clients concerning [brief description of the dispute].

1. [Statement of position — neutral, not adversarial.]
2. [Proposal — sum, terms, mechanism.]
3. [Time limit for acceptance.]
4. Subject to acceptance on these terms, the matter will be compromised on the basis of [release / settlement deed / consent order].

This letter is intended to be confidential and may not be disclosed to the court without our written consent.

Yours faithfully,

[Signature]

### Without Prejudice Save As To Costs

**WITHOUT PREJUDICE SAVE AS TO COSTS**

[Date]

[Recipient]

Dear Sirs,

**Re: [Matter]**

This letter is written without prejudice save as to costs.

1. Our client offers [to pay / to accept] £[X] in full and final settlement of the [dispute / claim / counterclaim].
2. The offer is open for acceptance for [21] days from the date of this letter.
3. The sum is [inclusive / exclusive] of [costs / interest / VAT].
4. Acceptance will be by [signed agreement / consent order / written acceptance].

If the offer is not accepted, our client reserves the right to refer to this letter on the question of costs after judgment.

Yours faithfully,

[Signature]

## Markers

- `[FOOTING — review: this content reads more open than WP]`
- `[UNILEVER RISK — admission / threat / unambiguous impropriety language]`
- `[SEPARATION — keep open correspondence in a different letter]`

## What this skill does not do

- Make a labelled letter privileged that isn't substantively a settlement attempt.
- Provide costs-protection equivalent to Part 36 in the civil courts. For that, use `part-36-offer`.
- Cover Scottish "tenders" or NI equivalents.
