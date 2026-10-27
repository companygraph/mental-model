---
id: 01a13dc2-94f1-7e2e-882e-bdc4fb3881a9
source: Governance research
source-id: GD-39
kind: functional
modality: must
realization: Released
---

# A model leaves its store as Markdown

> Any state of a model can be exported to the Markdown form with its ids, and imported back unchanged.

## Why

A company's model belongs to no tool, and the export is what lets it leave one; it is also what every check and every agent reads today.

## Fit criterion

A state exported and imported again is the same state, and the exported files pass `companygraph check`. Today the model is that Markdown.

## Applies to

| Type | Entity |
| --- | --- |
| feature | A vocabulary to describe a company in |

## Realization

In v0.95.0 the model's only store is its Markdown pages, each with its `id` in frontmatter, and `companygraph check` reads those files directly; there is no other store, no export command and no import command, so the round trip is the identity. The `companygraph-export` skill builds a bundle for an agent and a Gemini notebook from the Markdown, but it is not an export of a state back into the form. A requirement that expects a second store to leave is met only because none exists; no test observes a state exported and imported again.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `bin/check-instance.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/bin/check-instance.mjs |
| `core/CONVENTIONS.md` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/core/CONVENTIONS.md |
