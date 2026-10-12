---
id: 01a1312d-e1c9-76ac-ac67-967bd4cc3315
source: Local
kind: functional
modality: must
---

# An edited vendored file is overwritten only by force

> A vendored file that was edited inside the instance is never overwritten unless the move is forced, and a forced move names it as overwritten.

## Why

A vendored file is core's or a pack's to hold and never edited in an instance, but an edit someone made there is still their work; a move that overwrote it silently would lose the edit and hide that the instance had drifted from its release.

## Fit criterion

Given a vendored file edited inside the instance, a move writes nothing and names the file, a check fails naming the file as not as the tooling wrote it and says the forced upgrade puts it back, and a forced move overwrites it and names it as overwritten.

## Applies to

| Type | Entity |
| --- | --- |
| feature | An instance is made and kept from one command |
| feature | Checks an instance runs |

## References

| What | URL |
| --- | --- |
| The checker | https://github.com/companygraph/meta-model/blob/main/bin/check-instance.mjs |
