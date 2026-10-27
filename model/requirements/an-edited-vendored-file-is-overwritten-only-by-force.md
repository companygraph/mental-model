---
id: 01a1312d-e1c9-76ac-ac67-967bd4cc3315
source: Local
kind: functional
modality: must
realization: Verified
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

## Realization

`lib/plan.mjs` refuses a whole `upgrade` that meets a vendored file edited in the instance, naming it and writing nothing; with `--force` the file is overwritten and `bin/companygraph.mjs` reports `overwritten, as --force asked: <path>`. A file deleted from the instance is written fresh and reported apart, never as overwritten. `check` fails naming the file as `not as the tooling wrote it, and it is not the instance's to edit — companygraph upgrade --force puts it back`. Tests: `a vendored file edited inside the instance refuses the whole upgrade, and --force takes it` (plan), `upgrade refuses when core was edited inside the instance, and --dry-run writes nothing`, `check fails on a vendored file that is not as the tooling wrote it` (asserts the file name, not the `--force` remedy sentence) and `upgrade refuses a skill of the instance's own under a name it would write, and --force takes it` (asserts the `overwritten, as --force asked` line, for a skill file). No test asserts the overwritten line for an edited core file through the CLI.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `verify/plan.test.mjs` | verifies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/plan.test.mjs |
| `verify/cli.test.mjs` | verifies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/cli.test.mjs |
| `lib/plan.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/lib/plan.mjs |

## References

| What | URL |
| --- | --- |
| The checker | https://github.com/companygraph/meta-model/blob/main/bin/check-instance.mjs |
