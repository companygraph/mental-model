---
id: 01a13dc2-94f1-721a-93d1-87cf36b7f413
source: Governance research
source-id: GD-11
kind: functional
modality: must
realization: Not released
---

# A change keeps the record of how it was accepted

> Every applied change keeps its difference, its discussion, each check's result and who applied it.

## Why

Whoever asks later why a change is in the model, a reviewer, an auditor or the KPI that counts merges past their checks, reads that record and nothing else.

## Fit criterion

A year after it was applied, any change shows what changed, what was said about it, what was checked and who applied it when. Today a pull request meets it.

## Applies to

| Type | Entity |
| --- | --- |
| feature | Checks an instance runs |

## Realization

The record of difference, discussion, check results and applier is kept by GitHub's pull request. No release stores or reads it back.
