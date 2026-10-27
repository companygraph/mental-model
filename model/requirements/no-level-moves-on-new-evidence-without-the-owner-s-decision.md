---
id: 01a1312e-3ffe-7742-8b2e-702f056892b8
source: Local
kind: functional
modality: must
realization: Released
---

# No level moves on new evidence without the owner's decision

> A claimed level in a profile is never changed by a document the agent read; a new level is proposed with the rows behind it and left as it is until the owner decides.

## Why

A level is a claim a person makes about themselves, and a document can show a skill without settling how well; an agent that moved the level on its own reading would put a claim in the person's voice that nobody made.

## Fit criterion

On an update where a new document would change a claimed level, the reconciliation shows the level as a proposal with the rows behind it, and the page keeps the old level until the owner says otherwise.

## Applies to

| Type | Entity |
| --- | --- |
| feature | A profile is written from a person's documents |

## Realization

The `companygraph-profile` skill, on Update, reads the profile and every experience it owns, shows the reconciliation (already held, new, held differently with both versions, left out) to the operator first, keeps every sentence already written, and says "A level the new evidence would change is proposed to the operator with the rows behind it, never rewritten on the way past"; in the Create path "A level is proposed from the rows under it and the rung's own definition, and the operator decides it." Nothing mechanical holds a level in place, and no test exercises the skill; the checker has no rule that a level was changed by an agent.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `agents/claude/skills/companygraph-profile/SKILL.md` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/agents/claude/skills/companygraph-profile/SKILL.md |

## References

| What | URL |
| --- | --- |
| The profile procedure | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-profile/SKILL.md |
