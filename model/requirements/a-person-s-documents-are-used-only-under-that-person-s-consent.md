---
id: 01a1312c-d8ca-7860-838e-396197f5aeba
source: Local
kind: functional
modality: must
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

## References

| What | URL |
| --- | --- |
| The consent procedure | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-consent/SKILL.md |
