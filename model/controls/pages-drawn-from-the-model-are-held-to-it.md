---
id: 01a0ffcb-b7cd-74a9-979b-fdc59b77c87c
source: Local
kind: detective
mode: automated
enforces:
  - The model is corrected first
---

# Pages drawn from the model are held to it

> A pull request to companygraph.io fails where a page drawn from the model differs from what the model, at the commit the site pins, would draw.

## How it is carried out

The site's CI, on every pull request, in the `verify` job the ruleset requires: `build:check` parses this model and the meta-model at the commits `source.json` pins and fails where the committed artifacts differ, and `pages:check` renders every region drawn from those artifacts and fails where the committed page differs, so a page edited by hand, or one the model no longer produces, cannot merge until the model is corrected and the page drawn again.

## Applies to

| Type | Entity | Owner |
| --- | --- | --- |
| phase | Integrate | Delivery |

## References

| What | URL |
| --- | --- |
| companygraph.io's CI | https://github.com/companygraph/companygraph.github.io/blob/main/.github/workflows/ci.yml |
