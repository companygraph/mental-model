---
id: 01a13dc2-94f1-7e08-830f-158210d64e95
source: Local
source-id: GD-03
kind: functional
modality: must
---

# A change is shown entity by entity

> The difference between two states of a model is given per entity, per field and per section, with an entity paired across a rename by its id.

## Why

The checks on a change compare an id, a decision's text and a label on either side of it, and a reviewer reads what changed in each entity; a difference by lines or rows, or one that reads a rename as a deletion and an addition, shows neither.

## Fit criterion

Renaming an entity shows as one entity whose name changed, and editing one field shows that field and nothing else. Today git's difference with rename detection, read after the checker puts both sides in one form, meets it.

## Applies to

| Type | Entity |
| --- | --- |
| feature | Checks an instance runs |
