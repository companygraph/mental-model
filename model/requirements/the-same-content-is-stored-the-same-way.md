---
id: 01a13dc2-94f1-74d3-835e-75498a9df9cc
source: Governance research
source-id: GD-18
kind: functional
modality: must
realization: Released
---

# The same content is stored the same way

> Two writers who make the same change store the same state, whichever editor each used.

## Why

A difference that is only form hides the change a reviewer has to read, and sets two writers disagreeing about nothing.

## Fit criterion

The same edit made in two editors produces no difference between the two states. Today the one Markdown form, held by `companygraph form`, meets it.

## Applies to

| Type | Entity |
| --- | --- |
| feature | A repository is held to one form and told which pins are behind |

## Realization

`companygraph form` holds a repository's Markdown to one form (markdownlint-cli2 at the pinned version with the family's custom rules), reports hits, and with fix rewrites a file into the form, after which the check passes. `ids --range` compares decisions after the form so a form-only difference is not read as a change. The editor plugin bundles the same form code. No test observes two editors producing the same state from the same edit.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `lib/form.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/lib/form.mjs |
| `verify/form.test.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/form.test.mjs |
