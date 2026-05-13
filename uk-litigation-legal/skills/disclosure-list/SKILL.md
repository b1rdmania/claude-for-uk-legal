---
name: disclosure-list
description: Builds a disclosure list and List of Documents for civil proceedings in England & Wales — distinguishing between (a) the Disclosure Pilot regime now permanent under Practice Direction 57AD (Business and Property Courts) and (b) standard disclosure under CPR Part 31 elsewhere. Includes Models A–E selection guidance for PD 57AD, disclosure review document (DRD) structure, and the disclosure certificate. Use when the user says "disclosure list", "PD 57AD", "Model C", "extended disclosure", "List of Documents", "N265", or needs to scope what must be disclosed.
argument-hint: "[--regime=pd57ad|cpr31] [--model=A|B|C|D|E]"
---

# /disclosure-list

1. Identify the regime — PD 57AD (Business and Property Courts: Commercial Court, Chancery Division, TCC, Circuit Commercial, IP, Financial List) or CPR Part 31 (everywhere else, including most county court multi-track cases).
2. Under PD 57AD: select the appropriate Extended Disclosure Model(s) (A–E) per issue. Initial Disclosure is also required.
3. Under CPR 31: apply "standard disclosure" (CPR 31.6) — documents on which a party relies, plus documents that adversely affect own case / support another party's case / are required by a relevant practice direction.
4. Build the List of Documents (N265 form under CPR; Disclosure Review Document under PD 57AD).
5. Apply privilege screening before disclosure.

---

# Disclosure list

## Which regime?

| Court / Division | Regime |
|---|---|
| Business and Property Courts (Commercial, Chancery, TCC, Circuit Commercial, IP, Financial List) | PD 57AD (Disclosure Pilot — now permanent) |
| Other High Court divisions, County Court, fast track and multi-track | CPR Part 31 |
| Small claims track | CPR 27.4 (limited disclosure on directions) |
| Family proceedings | FPR — separate regime not covered here |

## PD 57AD — Extended Disclosure Models

After Initial Disclosure (limited — documents relied on plus those required for the other party to understand the case), the parties agree or the court orders **Extended Disclosure** by issue, using one or more of:

| Model | What it requires |
|---|---|
| **A** | Disclosure confined to known adverse documents (no further search). |
| **B** | Limited disclosure — documents necessary to enable other parties to understand the case being advanced. No proactive search beyond what was done for Initial Disclosure. |
| **C** | Request-based search — disclosure of specific documents or narrow classes specified by request. The narrowest "real search" model. |
| **D** | Narrow search-based disclosure — search for documents likely to be relevant + adverse documents found. The PD 57AD equivalent of standard disclosure. |
| **E** | Wide search — like Model D but including the train-of-enquiry approach (Peruvian Guano style). Available only where necessary to fairly resolve issues, generally where strong reasons. |

Selection happens via the **Disclosure Review Document (DRD)** — a structured negotiation document parties complete and exchange.

## CPR Part 31 — standard disclosure

Disclose:
- Documents on which the party relies (CPR 31.6(a)).
- Documents which adversely affect own case, adversely affect another party's case, or support another party's case (CPR 31.6(b)).
- Documents the party is required to disclose by a relevant practice direction (CPR 31.6(c)).

The duty extends to documents in the party's control (in physical possession, with right to possession, or right to inspect: CPR 31.8).

## Inputs

- Court / division (drives regime).
- Issues for disclosure (PD 57AD) or pleaded issues (CPR 31).
- Custodians (employees, agents, advisers).
- Data sources (email, file shares, document management, messaging apps — including WhatsApp / Signal, dataroom platforms).
- Date range.
- Privilege scope (advice privilege, litigation privilege, WP, common-interest).
- Confidentiality (commercially sensitive, regulatory, third-party).
- Foreign data protection (GDPR — Article 6/49 lawful basis for transfer).

## Workflow

### Step 1 — Regime check
B&P Courts → PD 57AD. Otherwise CPR 31.

### Step 2 — Initial Disclosure (PD 57AD)
Each party serves with Statements of Case: documents relied on + those required for other parties to understand. List of Issues for Disclosure follows in the DRD.

### Step 3 — Issues for disclosure (PD 57AD only)
A focused list — not the same as pleaded issues. Should be issues that disclosure will actually inform.

### Step 4 — Model selection per issue (PD 57AD)
Each issue gets a model. Default to Model C (request-based) where possible; Model D for broader issues; Model E only in exceptional cases.

### Step 5 — Custodian / data-source mapping
Who held the relevant documents; where the data lives; what platforms (Outlook / Gmail / Teams / Slack / WhatsApp / dataroom / paper).

### Step 6 — Search methodology
- Date ranges.
- Custodians.
- Data sources.
- Keywords (PD 57AD requires keyword lists and dedupe approach to be agreed).
- Use of technology-assisted review (TAR / predictive coding) — disclose use in the DRD.

### Step 7 — Privilege review
- Advice privilege: communications between solicitor and client for the purpose of legal advice.
- Litigation privilege: communications with third parties (witnesses, experts) where the dominant purpose is for litigation reasonably contemplated.
- WP: settlement correspondence.
- Common interest: shared legal interest with a third party (insurer, co-defendant).

Privileged documents are listed by description, not produced. Redaction of privileged parts is permissible.

### Step 8 — List of Documents

**CPR 31 — N265 List of Documents (or equivalent):**

Three parts:
- Part 1: documents in control, available for inspection.
- Part 2: documents in control, but right or duty to withhold from inspection (privilege).
- Part 3: documents that have been but are no longer in control (when and how parted with).

Plus the **Disclosure Statement** (signed personally — CPR 31.10) certifying the search and the duty.

**PD 57AD — Disclosure Certificate**

Signed by the party (not the solicitor) certifying the search complied with the order and disclosure obligations under the PD.

## Output template (CPR 31)

# List of Documents — [Case name and claim number]

## Part 1: Documents in our client's control which we do not object to producing for inspection

| ID | Date | Description | Custodian / source |
|---|---|---|---|
| C/1 | [date] | [description] | [custodian] |

## Part 2: Documents in our client's control which we object to producing for inspection

| ID | Date | Description | Ground |
|---|---|---|---|
| C/P/1 | [date] | [generic description] | Legal advice privilege |
| C/P/2 | [date] | [description] | Litigation privilege |
| C/P/3 | [date] | [description] | Without prejudice |

## Part 3: Documents which were but are no longer in our client's control

| Date | Description | When and how parted with | Whereabouts believed |
|---|---|---|---|

## Disclosure Statement (CPR 31.10)

I, [name], state:
1. My address is [...]. I am [position].
2. I have been authorised to make this disclosure statement on behalf of [party].
3. I am familiar with the issues in this case as set out in [pleadings].
4. I conducted a search for documents that I am required to disclose in accordance with [order / standard disclosure / agreed scope].
5. The search covered [custodians, data sources, date range, keywords].
6. I did not search for [excluded sources — eg paper archives older than 7 years, dormant servers] — give reasons.
7. I certify I understand the duty to disclose and to the best of my knowledge I have carried it out.

Signed: [party]
Date: [date]

## Output template (PD 57AD Disclosure Review Document, simplified)

# Disclosure Review Document — [Case]

## Section 1A: Initial Disclosure
[Complete — list of documents already provided.]

## Section 1B: Issues for Disclosure
| No. | Issue | Proposed Model | Reasons |
|---|---|---|---|
| 1 | [issue 1] | C | [...] |
| 2 | [issue 2] | D | [...] |

## Section 2: Custodians, sources, date range, keywords
[Table — agreed or proposed per issue.]

## Section 3: Technology
- Use of TAR / predictive coding: [yes/no, model]
- De-duplication, near-duplication, threading: [methodology]

## Section 4: Cost estimate
[Per CPR Part 47 / PD 57AD requirement.]

## Markers

- `[REGIME — confirm court division]`
- `[PRIVILEGE — flagged but not yet reviewed]`
- `[GDPR — cross-border transfer requires Art 6/49 basis]`
- `[SME VERIFY — Model selection per issue]`

## What this skill does not do

- Run the search. It scopes and lists.
- Decide privilege. Counsel reviews flagged documents.
- Cover Scottish / NI procedure (Commission and Diligence; Schedule 1 RCS).
