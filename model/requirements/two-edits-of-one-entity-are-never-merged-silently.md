---
id: 01a13dc2-94f1-7dae-8f43-257cf487aba1
source: Governance research
source-id: GD-09
kind: functional
modality: must
---

# Two edits of one entity are never merged silently

> Where two changes edit the same part of one entity, the second is refused until someone resolves the conflict.

## Why

An edit lost without a word is a fact the model held and no longer holds, and nobody decided to drop it.

## Fit criterion

Two changes edit one field of one entity, and the second cannot be applied until the conflict is resolved by hand. Today git's merge conflict meets it.

## Applies to

| Type | Entity |
| --- | --- |
| product | CompanyGraph Core |
