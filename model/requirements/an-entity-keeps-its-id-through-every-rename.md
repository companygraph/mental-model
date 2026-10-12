---
id: 01a1312c-aa8a-700b-9378-a8cab3147d09
source: Local
kind: functional
modality: must
---

# An entity keeps its id through every rename

> An entity carries one id for as long as it exists, through every rename and every language it is written in.

## Why

A page's name is what a reader sees and what the company may change; a system outside the model, a server's edge, a site's link or a test's citation, needs something that does not change when the name does. An edge that joined names would break on every rename, and a reader could not tell a renamed entity from a removed one.

## Fit criterion

A page renamed and the graph drawn again still has every edge joining the same id; and a commit that changes an id already on the default branch, a rename of it included, fails the range check a pull request runs.

## Applies to

| Type | Entity |
| --- | --- |
| product | CompanyGraph Core |

## References

| What | URL |
| --- | --- |
| The identifier schema | https://github.com/companygraph/meta-model/blob/main/core/identifier-schema.md |
