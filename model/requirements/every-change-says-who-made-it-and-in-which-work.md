---
id: 01a13dc2-94f1-7da6-a8c7-975fe347bb2a
source: Governance research
source-id: GD-05
kind: functional
modality: must
follows:
  - A commit keeps the author it was made with
realization: Verified
---

# Every change says who made it and in which work

> Every change records its author, the person accountable for it, its time and the process, phase and track it was made in.

## Why

The seat check holds an author to a seat its phase lists, and a later reader asks who made a change and in which work; neither can be answered from a change that does not say.

## Fit criterion

A change without an author, a process or a phase is refused, and every applied change shows all of them. Today a commit's author, committer, date and trailers meet it.

## Applies to

| Type | Entity |
| --- | --- |
| feature | Checks an instance runs |

## Realization

`companygraph commits` (through `judgeCommit` in `lib/seats.mjs`) refuses a commit with no Process trailer, no Phase trailer, a process that is none of the instance's or a phase that is none of the process's, and says that git reads trailers only from the last paragraph. The author is judged against the seats at the instance's domain. A commit shows its author, committer and date through git. The refusal runs at commit time and on each pull request, as for the seat check. An owner's commit and a bot's pass without trailers, so a change by those is not refused for lacking them.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `lib/seats.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/lib/seats.mjs |
| `verify/seats.test.mjs` | verifies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/seats.test.mjs |
