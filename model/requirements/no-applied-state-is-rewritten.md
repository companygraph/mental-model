---
id: 01a13dc2-94f1-74fe-bffd-6a45f0cf0173
source: Local
source-id: GD-04
kind: functional
modality: must
follows:
  - What is cited from outside the model is not rewritten
---

# No applied state is rewritten

> A state that changes were applied to is never rewritten or deleted.

## Why

Pins, answers and pages cite states by id, and a rewritten state leaves each of those citations pointing at something that now says another thing.

## Fit criterion

An attempt to rewrite or delete a past state is refused and the refusal is recorded. Today the ruleset's refusal of a force push and of a deletion meets it.

## Applies to

| Type | Entity |
| --- | --- |
| product | CompanyGraph Core |
