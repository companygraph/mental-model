---
id: 01a1312d-b350-7d3e-bf3f-9fde788ef9dd
source: Local
kind: functional
modality: must
realization: Verified
---

# A new instance passes its checks on its first day

> An instance the command writes passes the checks of the release that wrote it, with nothing in its model but the stubs.

## Why

A company that starts a model and meets a failing check before it has written a fact learns that the tooling, not the company, is what fails; the first run is where trust in the checks is won or lost.

## Fit criterion

A folder made with Make a model, checked at the release that made it, passes with no finding.

## Applies to

| Type | Entity |
| --- | --- |
| feature | An instance is made and kept from one command |

## Realization

`companygraph init` writes the vendored core, the stub model and the manifest, and the release's tests check the result: `an instance init writes passes the mechanical checks on its first day` runs `init` in a temp folder and asserts no failure from `checkInstance`; the menu's Make a model test, the `--folders` test and the pack tests (`requirements`, `organization`, `landscape`) do the same, and a test runs the `check` command on a fresh instance and asserts exit 0. The folder is checked at the release that made it, as the criterion asks.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `verify/cli.test.mjs` | verifies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/cli.test.mjs |
| `lib/plan.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/lib/plan.mjs |

## References

| What | URL |
| --- | --- |
| The command-line specification | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-09-20-the-cli-design.md |
