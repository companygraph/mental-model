---
id: 01a13dc2-94f1-7bd6-ab2d-41d4fb568509
source: Governance research
source-id: GD-12
kind: functional
modality: must
realization: Not released
---

# A change is applied only once its checks have passed

> A change is applied to the model only once every check the model requires has passed on it.

## Why

A check that can be skipped is advice; an instance's checks govern only where a change that fails them cannot land.

## Fit criterion

A change whose required check failed, or never ran, cannot be applied. Today the ruleset's required status checks meet it.

## Applies to

| Type | Entity |
| --- | --- |
| feature | Checks an instance runs |

## Realization

Nothing in a release refuses to apply a change whose required check failed or never ran. The only mechanism is the branch ruleset's required status checks, which GitHub provides and the family's conventions describe (`conventions/WORKING.md`, which says a ruleset requires the `conventions` job by its job id) without any product enforcing it. The checks themselves exist (`companygraph check`, `ids --range`, `commits --range` in the instance-check workflow), but the refusal to apply belongs to GitHub.
