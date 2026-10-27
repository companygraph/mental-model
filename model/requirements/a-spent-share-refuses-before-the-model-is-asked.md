---
id: 01a1312d-35b6-7630-a4fb-9c699de761ef
source: Local
kind: constraint
modality: must
realization: Verified
---

# A spent share refuses before the model is asked

> Once the hour's, the day's or the month's share the deployment wrote down is spent, a message is refused before any request to the language model is made.

## Why

A chat open to anyone who turns up spends money per message, and the ceiling is what lets the company leave it open; a refusal made after the model was asked has already spent what the ceiling was there to keep.

## Fit criterion

With the day's share spent, a message is refused, no request reaches the model, the refusal names the next midnight UTC as the moment it lifts, and the question is kept with the refusal's code.

## Applies to

| Type | Entity |
| --- | --- |
| feature | A visitor asks the model |

## Realization

The meter reserves an estimate before each call to the language model and refuses with `over_day`, `over_month` or `over_user_month` before the request is made; the hour is a per-address bucket that refuses with `busy`. A spent day names the next midnight UTC in `retryAt`, which the response also carries as `Retry-After`. The refused message's question is kept with the refusal's code. Tests check that the meter rejects with `over_day` and `retryAt` of the next midnight UTC, that a spent day refuses a second call with the model asked once, that a spent month is refused over HTTP before the stream, that the model is never asked when the meter or the shape refuses, and that the kept line carries `refused: "over_month"`. No single test starts with the day spent and checks all four things at once; the kept-line test uses the month.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `test/meter.test.mjs` | verifies | https://github.com/companygraph/chat-server/blob/v0.38.3/test/meter.test.mjs |
| `test/loop.test.mjs` | verifies | https://github.com/companygraph/chat-server/blob/v0.38.3/test/loop.test.mjs |
| `test/http.test.mjs` | verifies | https://github.com/companygraph/chat-server/blob/v0.38.3/test/http.test.mjs |
| `lib/meter.mjs` | satisfies | https://github.com/companygraph/chat-server/blob/v0.38.3/lib/meter.mjs |

## References

| What | URL |
| --- | --- |
| The design of one message answered | https://github.com/companygraph/chat-server/blob/main/docs/design/answering.md |
