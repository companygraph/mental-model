---
id: 01a13dc2-94f1-7d4b-9185-87bb28e1832d
source: Governance research
source-id: GD-31
kind: functional
modality: must
follows:
  - The model is corrected first
realization: Released
---

# A published page is checked against the state it names

> Every page published from a model is checked against what the state it names would draw.

## Why

A page edited by hand, or drawn from another state, says something the model does not, and the model is corrected first and the page drawn again.

## Fit criterion

A page whose content differs from what its named state draws fails its site's check. Today `pages:check` and `build:check` in each site's required `verify` job meet it.

## Applies to

| Type | Entity |
| --- | --- |
| feature | The vocabulary on the web |

## Realization

The site's `build/pages.mjs --check` (`pages:check`) runs each renderer in check mode and exits 1 where a region the site derives from the model differs from what the committed artifacts draw, and `build/build.mjs --check` (`build:check`) fails where `example.json`, `model.json` or `company.json` is not what the pinned commit parses to; both run as steps of the `verify` job in `.github/workflows/ci.yml`. A test in the site checks the JSON-LD renderer's check mode, that a second run is byte-identical, reports nothing and refuses a graph it does not own. No test changes a page by hand and checks that the whole `pages:check` fails. That the job is required before a change is applied is GitHub's ruleset and is not part of this level.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `build/pages.mjs` | satisfies | https://github.com/companygraph/companygraph.github.io/blob/3f8e4a25f599cc0e3c77cce8cce17e585d7a6b0e/build/pages.mjs |
| `.github/workflows/ci.yml` | satisfies | https://github.com/companygraph/companygraph.github.io/blob/3f8e4a25f599cc0e3c77cce8cce17e585d7a6b0e/.github/workflows/ci.yml |
| `build/renderers.test.mjs` | satisfies | https://github.com/companygraph/companygraph.github.io/blob/3f8e4a25f599cc0e3c77cce8cce17e585d7a6b0e/build/renderers.test.mjs |
