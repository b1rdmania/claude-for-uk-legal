# Contributing

Thanks for considering a contribution.

This project is a set of UK-jurisdiction plugins for Claude that produce drafts and analysis for solicitor review. Accuracy and discipline matter more than feature surface — a wrong skill is worse than a missing one.

## Ground rules

1. **No invented law.** Every legal assertion in a SKILL.md must be traceable to a statute, rule, practice direction, or named authority. Generic "lawyers usually do X" is not enough.
2. **Cite the source.** Statutes by short title and section. Rules by CPR Part and rule number. Cases by neutral citation (or pre-2001 reporter). Practice directions by number.
3. **Solicitor in the loop is the design assumption.** Skills produce drafts. Skills do not produce final deliverables. Don't soften this.
4. **Time-limit gates and privilege gates are unbypassable.** If you touch a skill that has one, the gate stays.
5. **No hallucinated authority.** If you don't know the citation, mark `[CITE NEEDED]`. Don't fabricate one.

## What we particularly want

- Corrections from practising UK lawyers. Please flag your role (eg "litigation solicitor, 8 PQE, Big4 firm") in your PR description — not as a credential check but because the discipline shifts when the corrector is in practice.
- New skills that fill specific gaps (interim relief, security for costs, possession claims, Vento-band quantum analysis).
- New plugins for adjacent practice areas (`uk-property-legal`, `uk-corporate-legal`, `uk-privacy-legal`).
- Better source attribution in existing skills.
- MCP connectors for Find Case Law, legislation.gov.uk, and the CPR.

## What we don't want

- Generic legal-AI commentary that doesn't change the substantive output.
- Skills that produce "legal advice" rather than draft outputs.
- Skills that drop the solicitor-review framing.
- Skills that lift US-jurisdiction patterns without translating to UK doctrine.

## Skill structure

Every SKILL.md follows the same shape:

```
---
name: skill-name
description: when this skill applies + trigger phrases the user might use
argument-hint: "[args]"
---

# /skill-name

[Numbered top-line workflow — what the skill does, in order.]

---

# [Skill name]

## Purpose

## Workflow

## Output template

## Markers

## What this skill does not do
```

Match this structure for consistency.

## PRs

1. Fork the repo.
2. Create a feature branch.
3. Add or change one skill per PR where possible.
4. Update the plugin README and the top-level README if you've added a skill.
5. Run a sanity test: invoke the skill against a realistic input in Claude Code and check the output.
6. Open the PR with a description of what changed and why.

## CLA

This project uses a Contributor License Agreement to allow the maintainer to dual-licence the code in future for commercial distribution. By submitting a PR you agree your contribution is licensed under Apache 2.0 *and* granted to the project under terms that permit future relicensing. The CLA workflow is on the roadmap; until then, by submitting a PR you confirm you have authority to grant these rights.

## AI-generated contributions

AI-assisted code and content is welcome. AI-fabricated authority is not. If you used an LLM to draft a skill, verify every citation and every statutory reference manually before submitting.

## Issues

For:
- Bug reports — what happened, what you expected, the prompt/inputs.
- Skill requests — what you'd want it to do, what existing skill it sits next to.
- Coverage gaps — Scottish / NI extensions, specific protocols not yet covered.
- Corrections — link to the authority that says the skill is wrong.

## Code of conduct

Be civil. Disagree with reasoning, not people.
