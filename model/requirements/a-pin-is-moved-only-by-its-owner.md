---
id: 01a1312e-4f0b-7c41-9bd7-ed1c2ab85441
source: Local
kind: functional
modality: must
realization: Verified
---

# A pin is moved only by its owner

> No pin a repository declares is moved by the machinery that reads it; a pin moves only in a commit the owner makes that says why.

## Why

A pin is editorial: a release or a commit behind is intent until the owner says it is drift, and a bot that moved pins would turn every upstream release into a change nobody decided.

## Fit criterion

A pins file whose tooling pin names a tag older than the upstream's newest is reported as behind, naming the newest tag, with nothing written and an exit of 0.

## Applies to

| Type | Entity |
| --- | --- |
| feature | A repository is held to one form and told which pins are behind |

## Realization

`companygraph pins` only reports: a behind pin gives exit 0 and names the newest tag, and the command writes nothing to the repository (its comment says a pin behind is intent until the owner says it is drift). Nothing in the release moves a pin on its own; `upgrade` moves the manifest only when the owner runs it, and leaves a family instance's own `pins.json` as it is (tested).

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `verify/cli.test.mjs` | verifies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/cli.test.mjs |
| `lib/pins.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/lib/pins.mjs |

## References

| What | URL |
| --- | --- |
| The pins reader | https://github.com/companygraph/meta-model/blob/main/lib/pins.mjs |
