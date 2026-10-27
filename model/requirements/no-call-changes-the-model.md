---
id: 01a1312d-a32d-711b-bcd8-29582f3f4110
source: Local
kind: constraint
modality: must
realization: Released
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

## Realization

All fourteen tools carry the annotation `readOnlyHint: true, openWorldHint: false`, and a test lists the tools and checks every annotation. The server builds an in-memory snapshot at start and answers from it; `lib/` has no file or network write, and the only writes in the package are the build commands (`snapshot`, `deploy`), which are not tools. No test calls every tool and then compares the repository it served byte for byte, so the second half of the fit criterion rests on reading the code and not on a test.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `test/server.test.mjs` | satisfies | https://github.com/companygraph/mcp-server/blob/v0.69.0/test/server.test.mjs |
| `lib/tools.mjs` | satisfies | https://github.com/companygraph/mcp-server/blob/v0.69.0/lib/tools.mjs |

## References

| What | URL |
| --- | --- |
| The strategy, with what it rules out | https://github.com/companygraph/mental-model/blob/main/model/strategies/read-only-server-strategy.md |
