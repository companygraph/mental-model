---
id: 01a1312d-a32d-711b-bcd8-29582f3f4110
source: Local
kind: constraint
modality: must
---

# No call changes the model

> The server has no write path: no tool an agent calls changes the model, which moves only by a commit to its repository and a new pin.

## Why

A company serving its model to agents should not have to decide whether to trust one with changing it. A write path would make that decision for every company at once, and the model is corrected where it is mastered, in its repository, under the review every change there gets.

## Fit criterion

Every tool the server lists carries the annotation that it only reads, and no call made over the server's whole surface changes a byte of the repository it serves.

## Applies to

| Type | Entity |
| --- | --- |
| feature | An agent reads the model |

## References

| What | URL |
| --- | --- |
| The strategy, with what it rules out | https://github.com/companygraph/mental-model/blob/main/model/strategies/read-only-server-strategy.md |
