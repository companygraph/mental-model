---
id: 01a1312c-aa8a-700b-9378-a8cab3147d09
source: Local
kind: functional
modality: must
realization: Released
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

## Realization

The parser in `lib/instance.mjs` hands out each entity by the id its page carries and draws every edge between ids (`edges.some(e => e.to === id)`, no edge names a path), so a renamed page keeps its edges. `companygraph ids --range` and `idChangesOf` fail a commit that changes an id already on the default branch, including across a rename, naming the old path; the instance workflow runs it on every pull request over the whole history. Tests: `an entity with an id is handed out by it, and keeps its path as address`, `a rename that changes the id fails, naming the old path too`, `a rename that keeps its id ... pass` and `ids --range refuses a commit that changed an id, across a rename`. Missing is a test that renames a page and redraws the graph to compare edges. Id retention across languages is not observed.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `verify/ids.test.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/ids.test.mjs |
| `verify/instance.test.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/instance.test.mjs |
| `.github/workflows/instance-check.yml` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/.github/workflows/instance-check.yml |

## References

| What | URL |
| --- | --- |
| The identifier schema | https://github.com/companygraph/meta-model/blob/main/core/identifier-schema.md |
