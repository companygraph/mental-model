---
id: 01a13135-072e-7d81-b46c-60b805711072
source: Local
kind: functional
modality: must
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

## References

| What | URL |
| --- | --- |
| The plan an upgrade follows | https://github.com/companygraph/meta-model/blob/main/lib/plan.mjs |
