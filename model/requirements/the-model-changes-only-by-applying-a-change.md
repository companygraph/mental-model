---
id: 01a13dc2-94f1-7c38-908e-ae0d7baa4bd0
source: Governance research
source-id: GD-19
kind: functional
modality: must
---

# The model changes only by applying a change

> The current state of a model changes only when a change is applied to it, never by a direct write.

## Why

Every guarantee the gate gives holds only for the changes that pass through it.

## Fit criterion

A direct write to the current state is refused for every account. Today the ruleset's pull request rule meets it.

## Applies to

| Type | Entity |
| --- | --- |
| feature | Checks an instance runs |
