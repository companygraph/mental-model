---
id: 01a10a8f-21f0-790c-abf7-f1eede82992a
source: Local
emitted-by: Message
---

# Answer checked

> Every claim of an answer was read back against the tool answers that carried the entities it names, before the answer ended.

## Payload

| Attribute | Term | Type | Many | Description |
| --- | --- | --- | --- | --- |
| Claims | Claim | | yes | Each claim with its place, the entities it names, its verdict and its probability |
| Threshold | | number | | The probability above which the page marks a claim not carried, empty where none is measured, as for an answer written in German |

## References

| What | URL |
| --- | --- |
| The event, `verdict` | https://github.com/companygraph/chat-server/blob/main/docs/INTERFACE.md |
| Implementation | https://github.com/companygraph/chat-server/blob/main/lib/verdict.mjs |
