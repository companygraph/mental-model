---
id: 01a13dc2-94f1-74b8-b710-e1b987fc8345
source: Governance research
source-id: GD-16
kind: functional
modality: must
realization: Released
---

# A page is checked as it is written by the gate's own checks

> A page is checked while it is written, by the same checker and the same schemas as the gate it will pass.

## Why

A writer who meets a failure only at the gate writes against the schema all day without seeing it, and a different checker in the editor would hold the page to a different model.

## Fit criterion

Before the change is proposed, an editor shows the failure the gate would report for the same page. Today the editor plugin, which bundles the checker at the instance's release, meets it.

## Applies to

| Type | Entity |
| --- | --- |
| feature | Checks while a file is edited |

## Realization

The Obsidian plugin 0.34.0 depends on `companygraph-meta-model` at v0.94.0 and calls `checkInstance`, the gate's own checker, on the vault's files each time they change, then shows each failure located in its page and a status line ("complies" or a failure count) with a note when the instance's pin differs from the bundled checker. The plugin bundles one fixed checker and not the instance's release, so it shows what that release would report, and the pin note is the only sign of a difference. `test/model.test.ts` observes the model builder's failures, not the editor's display.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `src/model.ts` | satisfies | https://github.com/companygraph/obsidian-plugin/blob/0.34.0/src/model.ts |
| `test/model.test.ts` | satisfies | https://github.com/companygraph/obsidian-plugin/blob/0.34.0/test/model.test.ts |
