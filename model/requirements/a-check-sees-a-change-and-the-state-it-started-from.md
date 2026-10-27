---
id: 01a13dc2-94f1-7d37-a822-5fbf43cdab35
source: Governance research
source-id: GD-14
kind: functional
modality: must
realization: Verified
---

# A check sees a change and the state it started from

> A check run on a change is given the whole proposed state and the state the change started from.

## Why

Some checks hold a change rather than its result, an id that changed, a decision rewritten, a label moved, a change's seat, and each of them needs both sides.

## Fit criterion

The id check refuses a change that alters an id and passes one that does not, reading only what its run was given. Today `companygraph ids --range` over a pull request's base and head meets it.

## Applies to

| Type | Entity |
| --- | --- |
| feature | Checks an instance runs |

## Realization

`companygraph ids --range <base>..<head>` reads the pages at both ends of the range from git and nothing else. It fails a change to an id across a rename, naming both sides, and passes a rename that keeps its id and a page that gains its first id. It also holds a decision and a label to what the range did, compared after the form, and refuses a three-dot range or a base with no common commit. The id check against the default branch is tested for refuse and pass.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `verify/cli.test.mjs` | verifies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/cli.test.mjs |
| `verify/ids.test.mjs` | verifies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/ids.test.mjs |
