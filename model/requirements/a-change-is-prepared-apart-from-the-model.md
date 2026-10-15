---
id: 01a13dc2-94f1-772c-95c9-1ed962c28c65
source: Governance research
source-id: GD-06
kind: functional
modality: must
---

# A change is prepared apart from the model

> A change to any number of entities is prepared apart from the model's current state, unseen by its readers until it is applied.

## Why

People and agents change the model at the same time, and a reader of the model, a server or a site must never see half a change.

## Fit criterion

Two changes edit the same entity and neither sees the other's edit before it is applied, and a reader of the current state sees neither. Today a branch, checked out in a worktree beside the clone, meets it.

## Applies to

| Type | Entity |
| --- | --- |
| product | CompanyGraph Core |
