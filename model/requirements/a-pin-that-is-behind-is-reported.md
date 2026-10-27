---
id: 01a13dc2-94f1-743b-b7f0-e3675d868409
source: Governance research
source-id: GD-26
kind: functional
modality: must
realization: Verified
---

# A pin that is behind is reported

> Every pin a consumer holds can be listed with how far it is behind what it pins.

## Why

A pin moves only on purpose, so whoever decides needs to see which are behind; a pin nobody sees is drift nobody chose.

## Fit criterion

One command lists each consumer's pins and how far each is behind. Today `companygraph pins` and the family report meet it.

## Applies to

| Type | Entity |
| --- | --- |
| feature | A repository is held to one form and told which pins are behind |

## Realization

`companygraph pins [<folder>]` reads the repository's `pins.json`, asks each upstream for its tags or head, and lists each pin as current, behind (naming the newest tag or commit), missing or unknown; pins the file does not declare are listed as unmanaged. `companygraph upgrade` writes the file into an instance and `adopt` into any repository. The family report that the criterion also names I did not find in the meta-model release, so a family-wide listing is not shown.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `verify/cli.test.mjs` | verifies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/cli.test.mjs |
| `verify/pins.test.mjs` | verifies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/pins.test.mjs |
| `lib/pins.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/lib/pins.mjs |
