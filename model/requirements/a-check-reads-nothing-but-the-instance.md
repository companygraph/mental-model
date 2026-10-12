---
id: 01a1312d-f16d-75d5-8b22-03bed2242fd5
source: Local
kind: constraint
modality: must
---

# A check reads nothing but the instance

> The checks over an instance read the instance's files and nothing else: no network, no filesystem beyond what they are handed, and no module but the readers they share with the parser.

## Why

The same checks run in a site's build, in the instance's workflow and in the tooling's own suite, and they give the same findings everywhere only when nothing outside the files they are handed can change the answer.

## Fit criterion

The checker's functions take a map of path to text and make no network call; the same instance checked in its workflow and in a site's build at the same release gives the same findings.

## Applies to

| Type | Entity |
| --- | --- |
| feature | Checks an instance runs |

## References

| What | URL |
| --- | --- |
| The meta-model, with what the checks are | https://github.com/companygraph/meta-model |
