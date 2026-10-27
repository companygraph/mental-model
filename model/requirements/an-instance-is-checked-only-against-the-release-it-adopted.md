---
id: 01a1312d-c2e9-7cd0-bdee-3dc0e8b33b31
source: Local
kind: functional
modality: must
realization: Verified
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

## Realization

`bin/check-instance.mjs` compares `manifest.tooling` with its own package version before reading any page and refuses with `move the pin and the workflow together, or call the release the manifest names`; it refuses a manifest whose `core.version` is newer than itself with `move the manifest's tooling and the workflow pin to v<x> together`; and `lib/plan.mjs` refuses `init` and `upgrade` toward a core newer than the running release before anything is written. The schemas are read from the instance's vendored core. Tests: `check says a manifest naming another release once` (exit 1, one message), `a core newer than the checker is refused naming both pins`, `a core newer than this tooling is refused by init before anything is written` and `upgrade refuses a core newer than itself, and writes nothing`. The test for the tooling mismatch asserts the refusal and exit code but not the move-both-together wording.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `verify/cli.test.mjs` | verifies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/cli.test.mjs |
| `bin/check-instance.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/bin/check-instance.mjs |
| `verify/plan.test.mjs` | verifies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/plan.test.mjs |

## References

| What | URL |
| --- | --- |
| The checker | https://github.com/companygraph/meta-model/blob/main/bin/check-instance.mjs |
