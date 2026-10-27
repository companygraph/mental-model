---
id: 01a13134-f779-7465-a3ee-fb54628d4340
source: Local
kind: functional
modality: must
realization: Released
---

# A fact no schema holds is written nowhere

> A fact a document or a page states that no schema has a place for is written nowhere in the model and noted nowhere beside it.

## Why

A schema is the contract for what the model holds, and a fact slipped in beside it, a birth date, a revenue, a headcount, would be held by nothing and checked by nothing; naming it by kind tells the owner what was left out without writing down what they chose not to hold.

## Fit criterion

A CV that states a birth date yields a profile with the date written nowhere and a report that names a fact of that kind left out; a company page that states a revenue, a headcount, a funding round or a founding year as an age yields no extraction and no note of it.

## Applies to

| Type | Entity |
| --- | --- |
| feature | A profile is written from a person's documents |
| feature | An agent does the work no script can, by the skills an instance ships |

## Realization

`companygraph-profile` takes out only what a schema has a place for and says a birth date, a nationality, a marital status, a salary or a grade "is not extracted, and not written down anywhere as a note either", and its Report lists "every fact left out because no schema holds it, named by kind and never by value". `companygraph-company` says a revenue, a headcount, a funding round, a founding year stated as an age or a customer count "are not extracted and not noted anywhere", with the same report line. That is the criterion's CV and company-page cases. The mechanical checks cannot see a fact no schema holds, and no test runs either skill, so whether an agent follows this is not observed.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `agents/claude/skills/companygraph-profile/SKILL.md` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/agents/claude/skills/companygraph-profile/SKILL.md |
| `agents/claude/skills/companygraph-company/SKILL.md` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/agents/claude/skills/companygraph-company/SKILL.md |

## References

| What | URL |
| --- | --- |
| The profile procedure | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-profile/SKILL.md |
| The company procedure | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-company/SKILL.md |
