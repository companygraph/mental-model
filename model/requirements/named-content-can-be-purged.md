---
id: 01a13dc2-94f1-7539-94a8-0d65ce4c1521
source: Local
source-id: GD-30
kind: functional
modality: must
---

# Named content can be purged

> Named content can be purged from every state that holds it, leaving a record of the purge.

## Why

A model that holds a company's operations will at some point hold a person's data or a secret it has to give up, and a store that can only add keeps them for good. Git cannot take content out of a state without rewriting every later state, which is why our models keep both out altogether.

## Fit criterion

After a purge the content cannot be read in any state, and the purge is listed with who made it, what kind of content it took and the states it touched. Today nothing meets it, and our models hold no such content.

## Applies to

| Type | Entity |
| --- | --- |
| product | CompanyGraph Core |
