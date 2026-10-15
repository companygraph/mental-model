---
id: 01a13dc2-94f1-7d37-a822-5fbf43cdab35
source: Governance research
source-id: GD-14
kind: functional
modality: must
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
