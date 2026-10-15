---
id: 01a13dc2-94f1-7333-bbee-5add1e1f9244
source: Governance research
source-id: GD-10
kind: functional
modality: must
follows:
  - A commit keeps the author it was made with
---

# Applying a change keeps its author

> Applying a change keeps the author it was made with.

## Why

An author replaced by whoever applied the change would let a change made under a wrong identity reach the model looking correct, and would hide which seat did the work.

## Fit criterion

An applied change shows the seat that made it, and apart from it the account that applied it. Today merging only with a merge commit, with squash and rebase turned off, meets it.

## Applies to

| Type | Entity |
| --- | --- |
| feature | Checks an instance runs |
