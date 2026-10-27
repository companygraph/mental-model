---
id: 01a13dc2-94f1-7e26-8f77-d0a1671dba58
source: Governance research
source-id: GD-08
kind: functional
modality: must
follows:
  - A state is read again before it is relied on
realization: Not released
---

# A change is applied only to the state it was checked on

> A change is applied only on top of the state its checks ran on, so a change whose base has moved is checked again on the current state first.

## Why

Two changes that each pass alone can break the model together, and checks run on an older state say nothing about the state a change lands on.

## Fit criterion

A change whose base has moved cannot be applied until its checks have passed on the current state. Today the required checks in strict mode, with main merged into the branch, meet it.

## Applies to

| Type | Entity |
| --- | --- |
| feature | Checks an instance runs |

## Realization

No release makes a change whose base has moved wait for its checks on the current state. The criterion names GitHub's required checks in strict mode, which is a repository setting and not a behavior of any released product. `ids --range` is written to cope with a branch behind its base (it reads from the merge base, tested in `verify/cli.test.mjs`) but it does not stop such a change from being applied.
