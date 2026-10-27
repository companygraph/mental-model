---
id: 01a13dc2-94f1-7a54-b549-f05bf31dd536
source: Governance research
source-id: GD-40
kind: functional
modality: must
realization: Released
---

# An agent works on a model through the skills it ships

> Every skill an instance ships runs against any state of the model, wherever the model is kept.

## Why

The agent pass, the procedures and the judge do the work no script can, and a store they cannot read leaves that work undone.

## Fit criterion

`companygraph-validate` runs against a state of the model and reports what it reports on the files. Today the skills read the files of a clone.

## Applies to

| Type | Entity |
| --- | --- |
| feature | An agent does the work no script can, by the skills an instance ships |

## Realization

Seven skills ship with an instance under `.claude/skills/`. `companygraph-validate` runs the mechanical checks and then reads each schema's writing rules against the entities in the files of the clone; the others read and write files under `model/`. Their only store is that clone, which is what the page says today, so the criterion that they run against any state wherever the model is kept holds for the one store there is and is untested for any other. Tests run the export skill's `build.py` and `verify.py` and the surface skill's `facts.py` over an instance `init` made, and check the skill names and hashes; no test runs a procedure (validate, profile, company, consent, judge) end to end, since each needs an agent.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `agents/claude/skills` | satisfies | https://github.com/companygraph/meta-model/tree/v0.95.0/agents/claude/skills |
| `verify/cli.test.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/cli.test.mjs |
