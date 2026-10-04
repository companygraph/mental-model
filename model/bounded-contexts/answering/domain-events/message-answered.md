---
id: 01a10042-60ca-7c2f-bef6-40b7c2de0380
source: Local
emitted-by: Message
---

# Message answered

> A visitor's message was answered to its end, from the commit the host last named, at a cost the meter has settled.

## Payload

| Attribute | Term | Type | Many | Description |
| --- | --- | --- | --- | --- |
| Model | | string | | The host's provenance, the commit the answer was read at |
| Spent | | number | | What the message cost, in input-equivalent tokens |
| Day left | | number | | What is left of today's share, in input-equivalent tokens |
| Cut | | boolean | | Present where the output limit stopped the answer mid-sentence |

## References

| What | URL |
| --- | --- |
| The event, `done` | https://github.com/companygraph/chat-server/blob/main/docs/INTERFACE.md |
