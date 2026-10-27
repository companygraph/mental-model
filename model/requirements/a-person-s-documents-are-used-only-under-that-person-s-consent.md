---
id: 01a1312c-d8ca-7860-838e-396197f5aeba
source: Local
kind: functional
modality: must
realization: Released
---

# A person's documents are used only under that person's consent

> Nothing from a person's documents or public pages is written into the model unless that person's consent is given, or the person is the owner modeling themselves.

## Why

A profile is written from CVs, diplomas and reference letters, and a company's instance from team pages that name people; each is a person's own, and a model that held facts about them without their word would be a second record of them they never agreed to. The owner's own documents need no one else's word, and asking would be noise.

## Fit criterion

Given documents of a person who is not the owner and whose consent is not given, the run writes nothing; given the owner modeling themselves, no consent is asked and the report says so in one line; and given a team page, a person whose consent is not given has their rows dropped and the run goes on without them.

## Applies to

| Type | Entity |
| --- | --- |
| feature | A profile is written from a person's documents |
| feature | An agent does the work no script can, by the skills an instance ships |

## Realization

`companygraph-consent` proposes a consent as needed for any person drawn from a source and as not needed for a person modeling themselves ("no, and the step is one line in the report"), takes only what the operator states, and treats a consent the operator cannot state as not given. `companygraph-profile` step 6 runs it before anything is written: for the owner modeling themselves "the step is one line in the report", and for any other person "a consent not given ends the run with nothing written". `companygraph-company` step 7 drops a person's rows whose consent is not given and goes on, and step 5 never mentions a struck person in the model. No test runs a procedure, and nothing mechanical reads consent.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `agents/claude/skills/companygraph-consent/SKILL.md` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/agents/claude/skills/companygraph-consent/SKILL.md |
| `agents/claude/skills/companygraph-profile/SKILL.md` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/agents/claude/skills/companygraph-profile/SKILL.md |
| `agents/claude/skills/companygraph-company/SKILL.md` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/agents/claude/skills/companygraph-company/SKILL.md |

## References

| What | URL |
| --- | --- |
| The consent procedure | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-consent/SKILL.md |
