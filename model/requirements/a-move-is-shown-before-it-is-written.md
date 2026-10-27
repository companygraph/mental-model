---
id: 01a1312d-d213-79b9-b25f-3ef12ecbec31
source: Local
kind: functional
modality: must
realization: Released
---

# A move is shown before it is written

> A move of an instance to another release lists every path it would write or remove, and writes only on a yes.

## Why

A move touches the vendored core, the packs and the procedures, and an owner who sees the list first can stop a move that would reach a file they did not expect; a move that wrote first would leave the owner reading a diff to find out what happened.

## Fit criterion

Move a model, picked on an instance on an older release, lists every path before writing one, and the instance is moved only on a yes to Go ahead.

## Applies to

| Type | Entity |
| --- | --- |
| feature | An instance is made and kept from one command |

## Realization

The menu entry `Move a model to <version>` in `bin/companygraph.mjs` runs `upgrade --dry-run` first, which lists every path as `write`, `remove` or `moved` (and marks the removals `--force` takes), then asks `Go ahead?` with a default of no and runs the real upgrade only on a yes. `upgrade --dry-run` writes nothing, which tests observe for a seats migration and an edited core. The only menu test for this entry runs on an instance already current (`nothing to do`), so the yes and no answers over a real move are not exercised. Moves that change files outside the planned lists (the gate hooks, `core.hooksPath`) are named in the same dry run in the cases tests cover.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `bin/companygraph.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/bin/companygraph.mjs |
| `verify/cli.test.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/cli.test.mjs |

## References

| What | URL |
| --- | --- |
| The command-line specification | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-09-20-the-cli-design.md |
