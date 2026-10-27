---
id: 01a13dc2-94f1-7e08-830f-158210d64e95
source: Governance research
source-id: GD-03
kind: functional
modality: must
realization: Partly released
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

## Realization

`companygraph ids --range <a>..<b>` compares the pages of two commits after putting both sides in the Markdown form, pairs a renamed page across the rename by its path in the range, and reports an id that changed (naming the old path), a decision rewritten or deleted and a label moved. That is a difference per entity for those three things. The release has no command that gives the whole difference of two states per entity, per field and per section, so editing one field and seeing that field and nothing else is met only by git's own difference plus the form.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `verify/cli.test.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/cli.test.mjs |
| `bin/companygraph.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/bin/companygraph.mjs |
