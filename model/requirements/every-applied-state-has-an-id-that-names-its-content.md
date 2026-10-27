---
id: 01a13dc2-94f1-7048-a23d-a118911279f7
source: Governance research
source-id: GD-01
kind: functional
modality: must
realization: Not released
---

# Every applied state has an id that names its content

> Every state of a model that changes were applied to has an id that names exactly that content and never any other.

## Why

A pin, a served answer and a published page each say which state of the model they come from, and that is worth something only while the name always means the same content.

## Fit criterion

Two reads of one state's id return the same content, byte for byte, at any later time, and a state that differs by one byte has another id. Today a git commit and its hash meet it.

## Applies to

| Type | Entity |
| --- | --- |
| product | CompanyGraph Core |

## Realization

The state id is git's commit hash. The release's manifest holds file hashes of vendored files, not a name for a state of the model, so nothing released supplies it.
