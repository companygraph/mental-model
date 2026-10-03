---
id: 01a0ffcb-9983-7c5d-811a-2e7f65a2a144
source: Local
kind: detective
mode: automated
enforces:
  - German follows reviewed English
---

# German left behind is found

> A pull request to companygraph.io fails where an English edit left its German unchanged, unless a commit says the German is right on purpose.

## How it is carried out

The site's CI, on every pull request, in the `verify` job the ruleset requires: `design german stale` compares the change with its base and fails for each element whose English moved while its German did not; a commit that names the element in a `German-unchanged:` trailer releases it.

## Applies to

| Type | Entity | Owner |
| --- | --- | --- |
| phase | Integrate | Delivery |

## References

| What | URL |
| --- | --- |
| companygraph.io's CI | https://github.com/companygraph/companygraph.github.io/blob/main/.github/workflows/ci.yml |
| The German stale check | https://github.com/robertblust/design#readme |
