---
id: 01a13dc2-94f1-74d8-9f42-d037407ef6b1
source: Governance research
source-id: GD-17
kind: functional
modality: must
realization: Verified
---

# A change names a seat its phase lists

> A change authored by a seat is refused unless the phase it names lists that seat.

## Why

The author of a change says which seat did the work, and that is true only where the seat is one the phase of the work lets do it.

## Fit criterion

A change by a seat the named phase does not list is refused when it is made and again before it is applied. Today the commit-msg hook and the seat check on each pull request meet it.

## Applies to

| Type | Entity |
| --- | --- |
| feature | Checks an instance runs |

## Realization

`companygraph commits` refuses a commit whose author is a seat the named phase does not list and exits 3. It runs when the commit is made, through the commit-msg hook that `conventions` v1.52.0 ships and that `companygraph init` writes into an instance, and again before the change is applied, through the `commits --range` step of the instance-check workflow on each pull request. The meta-model's tests observe the refusal for a message and for a range, naming the seat that does list the phase. Where the hook cannot run (no clone, offline) it lets the commit through with a sentence and leaves the refusal to the pull request, and a change can be applied without that workflow step if a repository omits it.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `verify/commits.test.mjs` | verifies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/commits.test.mjs |
| `.github/workflows/instance-check.yml` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/.github/workflows/instance-check.yml |
| `conventions/hooks/commit-msg` | satisfies | https://github.com/robertblust/conventions/blob/v1.52.0/conventions/hooks/commit-msg |
