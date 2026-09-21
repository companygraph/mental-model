---
source: Local
owner: Owner
executed-by:
  - Owner
gate-approvers:
  - Owner
escalation-authority: Owner
gate-to: Answer
---

# Triage

> Decide what kind of thing the gap is, and whether it is ours to fill.

## What it takes

A restated request naming what could not be written.

## Activities

1. The Owner decides which of four the gap is: vocabulary every kind of company needs, vocabulary only some kinds need, tooling, or no gap at all.
2. The Owner checks whether an existing type already carries the fact under another name, because a request for a second name for one thing is a finding about the first.
3. The Owner weighs it against the strategy: vocabulary enters core once a company has actually had to be described with it, so one request is evidence and is not yet that.
4. The Owner writes the classification and its reason in the issue.

## What it produces

| Deliverable | Description |
| --- | --- |
| Classification | Which of the four the gap is, with the reason, written in the issue |

## What it never does

- Never classifies a gap as core vocabulary on the strength of one request.
- Never leaves the reason out because the classification seems obvious.
- Never opens a specification; what happens next is Delivery's, and it starts from its own Shape.

## Gate

To leave Triage, all of these hold:

- The gap is classified as core vocabulary, pack vocabulary, tooling or no gap.
- The reason is written where the request was made.
- Where it is core vocabulary, the instance that had to be described with it is named.

Where they cannot be met, the Owner leaves the request open and says what would settle it, rather than classifying it to be finished with it.
