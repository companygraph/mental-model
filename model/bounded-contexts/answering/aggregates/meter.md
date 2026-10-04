---
id: 01a10042-5ed7-76ad-a6b4-2aa112bd4f7a
source: Local
root: Meter
---

# Meter

> No request to the model is made that would carry the day past its share or the month past its ceiling, however many messages are in flight on however many instances.

## Invariants

| Label | Invariant |
| --- | --- |
| INV-A12 | Every request to the model reserves an estimate before it is made and settles to what it cost once it answered; a request that failed between the two gives its reservation back. |
| INV-A13 | A reservation that would carry the day past its share or the month past its ceiling is refused and adds nothing, and the refusal names the moment it lifts: the next midnight UTC for the day, the first of the next month for the month. |
| INV-A14 | The day's share is a tenth of the month's ceiling. |
| INV-A15 | The day's count starts again at midnight UTC and the month's at the first of the month, and neither falls below zero. |
| INV-A16 | While the owner has switched the chat off, every reservation is refused. |
| INV-A17 | Cost is counted in input-equivalent tokens: input as it is, and cache writes, cache reads and output each at the model's price ratio to input, rounded up per request. |

## Handled commands

| Command | Emits | When | Description |
| --- | --- | --- | --- |
| Reserve for a request | | | Adds the estimate to the day and the month, or refuses where the chat is closed or a line would be crossed |
| Settle a request | | | Replaces the estimate with what the request cost |
| Read the standing | | | Gives the ceiling, the share, what the day and the month have spent and whether the chat is closed, without spending anything |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/chat-server/blob/main/lib/meter.mjs |
| The meter's unit | https://github.com/companygraph/chat-server/blob/main/docs/INTERFACE.md |
