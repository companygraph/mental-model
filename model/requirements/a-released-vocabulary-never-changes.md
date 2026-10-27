---
id: 01a13dc2-94f1-74ed-b43a-8fa44bf9c1a3
source: Governance research
source-id: GD-24
kind: functional
modality: must
realization: Not released
---

# A released vocabulary never changes

> A release of the vocabulary, core or a pack, never changes once it is made.

## Why

An instance adopts a release by naming it, and a release that moved would change the rules a model is held to without the model deciding.

## Fit criterion

An attempt by anyone but the Owner to move or delete a released version is refused. Today a tag, held by the release-tag ruleset, meets it.

## Applies to

| Type | Entity |
| --- | --- |
| feature | A vocabulary to describe a company in |

## Realization

A GitHub ruleset on release tags stands in today by refusing a move or deletion by anyone but the Owner. No release refuses it: `companygraph pins` reports a pin behind without recording what a tag pointed at, and the check of vendored files against the manifest fails an instance whose core was edited, which notices a change after the fact and prevents none.
