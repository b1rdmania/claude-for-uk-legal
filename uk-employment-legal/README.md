# uk-employment-legal

England & Wales employment-law plugin for Claude. Three skills: pre-action notice, fairness screening, and settlement-agreement review.

> Demo plugin. Drafts for solicitor review. Not legal advice.

## Skills

| Skill | What it does |
|---|---|
| [`/uk-employment-legal:lba-drafter`](./skills/lba-drafter/SKILL.md) | Drafts a Letter Before Action for an ET or civil claim. Surfaces the ET 3-month limit before generating — a polite pre-action letter doesn't stop the clock. |
| [`/uk-employment-legal:unfair-dismissal-screener`](./skills/unfair-dismissal-screener/SKILL.md) | Structures a Burchell + Polkey + ACAS Code analysis with an indicative risk view for a solicitor to verify. |
| [`/uk-employment-legal:settlement-agreement-review`](./skills/settlement-agreement-review/SKILL.md) | Flags apparent s.203 ERA condition gaps (in writing, named adviser, insurance, statement of conditions) for a solicitor to confirm, and reviews substantive terms. |

## Install

```bash
/plugin marketplace add https://github.com/b1rdmania/claude-for-uk-legal
/plugin install uk-employment-legal@claude-for-uk-legal
```

## Time limits

Most malpractice in employment law is missed limitation. Always confirm the latest-issue date with a date calculator — do not rely on a date computed in the output.

| Claim | Primary limit | Statute |
|---|---|---|
| Unfair dismissal | 3 months less 1 day from EDT | s.111 ERA 1996 |
| Discrimination | 3 months less 1 day from act / last act | s.123 EqA 2010 |
| Unlawful deduction | 3 months less 1 day from deduction | s.23 ERA 1996 |
| Equal pay | 6 months from end of employment | s.129 EqA 2010 |
| Redundancy payment | 6 months from relevant date | s.164 ERA 1996 |

ACAS early conciliation extends these via the s.207B "stop the clock" mechanism. The LBA does not.

## Coverage

England & Wales only. Not Scotland, Northern Ireland, or the tax tribunal. For multi-jurisdiction matters, run the relevant local plugin per jurisdiction.

## What this plugin doesn't do

- Send anything externally — outputs are drafts.
- Replace independent legal advice for the s.203 settlement-agreement adviser certificate.
- Compute limitation dates, tax, or quantum reliably — verify every figure with a solicitor.
- Cover the Employment Rights Bill 2025 day-one rights regime until the commencement order is in force.

## Status

`v0.1.0` — May 2026. Open to corrections from practising employment solicitors. Please flag your role in PR descriptions.
