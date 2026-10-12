---
id: 01a1312d-c2e9-7cd0-bdee-3dc0e8b33b31
source: Local
kind: functional
modality: must
---

# An instance is checked only against the release it adopted

> The checker that runs over an instance is the release its manifest names, and it reads the schemas from the core the instance vendored, so no release holds a model to rules it has not taken.

## Why

A release adds rules, and a company takes one when it decides to, in a commit that says why; a newer checker running over an older instance would fail pages for rules nobody there has read, and would make every release upstream a breaking change downstream.

## Fit criterion

A checker that is not the release the manifest names refuses before reading a page and says to move the pin and the workflow together; a manifest that vendors a core newer than the checker is refused with the same instruction; and a core tag newer than the release that runs is refused at init before anything is written.

## Applies to

| Type | Entity |
| --- | --- |
| feature | Checks an instance runs |
| feature | An instance is made and kept from one command |

## References

| What | URL |
| --- | --- |
| The checker | https://github.com/companygraph/meta-model/blob/main/bin/check-instance.mjs |
