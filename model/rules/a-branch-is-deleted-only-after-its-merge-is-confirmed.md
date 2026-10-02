---
id: 01a0fd97-0436-744d-bcc5-ada708012187
source: Local
modality: must
---

# A branch is deleted only after its merge is confirmed

> A branch is deleted as a step of its own, once its merge is confirmed, and never chained after the merge.

## Why

A delete chained after a merge runs even when the merge fails, and deleting a pull request's branch closes it, so a merge that failed would lose the change it was meant to take.

## Applies to

| Type | Entity | Owner |
| --- | --- | --- |
| phase | Integrate | Delivery |
| phase | Integrate | Contribution |
