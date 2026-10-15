---
id: 01a13dc2-94f1-7ef6-b0a1-702d8ac34b7e
source: Governance research
source-id: GD-07
kind: functional
modality: must
---

# A change is applied whole or not at all

> A change is applied to the model whole, as one new state, or not at all.

## Why

The checks hold the whole model, so a change applied in part leaves a state no check ever saw.

## Fit criterion

A change that fails while it is applied leaves the current state as it was. Today a merge commit meets it.

## Applies to

| Type | Entity |
| --- | --- |
| product | CompanyGraph Core |
