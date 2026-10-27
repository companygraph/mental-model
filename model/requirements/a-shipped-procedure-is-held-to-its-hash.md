---
id: 01a13135-072e-7d81-b46c-60b805711072
source: Local
kind: functional
modality: must
realization: Verified
---

# A shipped procedure is held to its hash

> Every procedure a release ships into an instance is recorded in the manifest with its hash beside the vendored core's, and a procedure edited in place fails the check by name.

## Why

An agent asked for judgment work should follow the procedure its instance names and not one improvised or quietly changed; held to a hash like the vendored core, a procedure that drifted is found by the same check that finds a drifted schema.

## Fit criterion

An instance written for an agent carries every procedure of the running release under the agent's skills folder with its hash in the manifest; a shipped procedure edited inside the instance fails the check on that file; and a procedure of the instance's own, under another name, is left alone by an upgrade.

## Applies to

| Type | Entity |
| --- | --- |
| feature | An agent does the work no script can, by the skills an instance ships |

## Realization

`init --agent claude` writes the seven shipped procedures under `.claude/skills/` and records each file's hash in the manifest beside the core's (`companygraph-company`, `-consent`, `-export`, `-judge`, `-profile`, `-surface`, `-validate`). `check` fails a skill edited in place with `<path>: not as the tooling wrote it`, exactly as for core; `upgrade` moves them and refuses an edited one. An instance whose manifest records no skills and holds skills of its own gets none written over them, and a skill under a name the release does not ship is not in the manifest and is not touched. Tests: `init writes the skills, hashed into the manifest like the core`, `check fails on a skill edited inside the instance, as on edited core`, `check fails on the company skill edited inside the instance`, `an instance whose manifest records no skills ... keeps its own where it holds any`. Skills are written for the `claude` agent only; the release names no other.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `verify/cli.test.mjs` | verifies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/cli.test.mjs |
| `verify/plan.test.mjs` | verifies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/plan.test.mjs |
| `lib/plan.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/lib/plan.mjs |

## References

| What | URL |
| --- | --- |
| The plan an upgrade follows | https://github.com/companygraph/meta-model/blob/main/lib/plan.mjs |
