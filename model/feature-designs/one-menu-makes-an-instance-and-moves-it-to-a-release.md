---
id: 01a10042-6412-794a-9686-6f04999c4952
source: Local
refines: An instance is made and kept from one command
contexts:
  - Vendoring
  - Checking
decisions:
  - Core is vendored into an instance at a release its manifest names
  - A release is its tag, and nothing we make is published to a registry
---

# One menu makes an instance and moves it to a release

> The command run with nothing after it opens a menu that makes an instance at the release that runs and later moves it to another, showing each move before it writes and refusing one that would overwrite an edit.

## Operational principle

Someone runs the command at a terminal, picks Make a model, names a folder and the company; the instance is made with core vendored under its unit's folder, every vendored file in the manifest with its hash and the workflow pinned to the same release, so the check passes at once; when a later release is run, Move a model lists what it would write and remove, and moves core, skills, manifest and workflow ref together on a yes.

## Scenarios

### SC-M1: A new folder becomes an instance that passes

Given a folder that does not exist, when Make a model is picked and the company named, then the instance is made with its manifest and starting entities, and checking the folder passes.

### SC-M2: A folder already claimed is refused whole

Given a folder that holds a `meta/` folder of its own, when the model is added beside its files, then nothing is written and the refusal names `meta/` as already there.

### SC-M3: A move is shown before it is made

Given an instance on an older release, when Move a model is picked, then every path the move would write or remove is listed, and the instance is moved to the release only on a yes to Go ahead.

### SC-M4: An edited vendored file stops the move

Given a vendored file edited inside the instance, when the instance is moved, then nothing is written and the file is named; moved with `--force`, it is overwritten and named as overwritten.

### SC-M5: A pack taken later

Given an instance made without a pack, when it is moved with `--pack software`, then the pack is vendored as a unit beside core, listed in the manifest and each root folder it adds is given a README once.

## Uses

| Type | Entity | Context |
| --- | --- | --- |
| concept-design | Manifest | Vendoring |
| concept-design | Vendored file | Vendoring |
| concept-design | Unit | Vendoring |
| domain-event | Instance made | Vendoring |
| domain-event | Instance moved to a release | Vendoring |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/bin/companygraph.mjs |
| Implementation | https://github.com/companygraph/meta-model/blob/main/lib/plan.mjs |
| The command-line specification | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-09-20-the-cli-design.md |
