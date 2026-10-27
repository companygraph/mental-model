---
id: 01a13dc2-94f1-7a46-a9b3-552f13563afe
source: Governance research
source-id: GD-15
kind: functional
modality: must
follows:
  - A check counts only when its output was seen
realization: Not released
---

# A check's output is kept with the change it checked

> The output of every check run on a change is kept and can be read from that change.

## Why

A check counts as passed only when its output was seen, and the output is what a reviewer and every later reader hold a report against.

## Fit criterion

The output of any check run on any applied change can be read from that change, its failures told apart from its notes. Today a check run's log, linked from its pull request, meets it.

## Applies to

| Type | Entity |
| --- | --- |
| feature | Checks an instance runs |

## Realization

Check output is kept by GitHub Actions as the log of a check run. No release keeps or reads it, and the checks only print to the run.
