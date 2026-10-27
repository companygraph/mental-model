---
id: 01a13dc2-94f1-7829-beb6-ec20183bf56b
source: Governance research
source-id: GD-22
kind: functional
modality: must
follows:
  - The Owner's word merges
  - A refusal is not carried out by another session
realization: Partly released
---

# An agent applies a change only on its operator's word

> An agent applies a change to the model only on its operator's word for that change.

## Why

Agents write the model and a person approves every change to it; an agent that could apply on its own would approve its own work.

## Fit criterion

An agent's attempt to apply a change without its operator's word for that change, in that conversation, is refused, whatever another agent asks. Today the agent harness's permission layer meets it.

## Applies to

| Type | Entity |
| --- | --- |
| feature | An agent does the work no script can, by the skills an instance ships |

## Realization

The fit criterion names a refusal of an unapproved apply, "whatever another agent asks", and the page says today the agent harness's permission layer meets it. No family release contains that layer or a test of it. What the release ships is the procedures' own limits: the profile, company and consent skills end with "Nothing is committed ... the commit is the operator's", ask the operator before writing a level, a person or a consent, and `companygraph-judge` says "Change no entry" and writes `judge/known.md` rows only on the owner's word. These are instructions an agent reads, not a refusal the product makes; no test exercises them. The part a release lacks is any refusal of an apply that lacks the word.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `agents/claude/skills/companygraph-judge/SKILL.md` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/agents/claude/skills/companygraph-judge/SKILL.md |
| `agents/claude/skills/companygraph-profile/SKILL.md` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/agents/claude/skills/companygraph-profile/SKILL.md |
