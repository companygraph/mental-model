---
id: 01a10042-6002-735b-aa63-ad043979bbef
source: Local
kind: entity
---

# Message

> One message a visitor sent and the answer to it: the conversation it ends, the rounds the model took, and what the answer cited and named. The next message in the same conversation is another message.

## Attributes

| Attribute | Type | Description |
| --- | --- | --- |
| Conversation | list of turns | The visitor's and the chat's turns that reach the model, the visitor's last |
| Page language | `en` or `de` | The language of the page it was sent from, which the answer takes only where the message's own words do not tell |
| Rounds | number | The requests the model answered |
| Spent | input-equivalent tokens | What its requests cost, as the meter counts it |
| Cut | boolean | Whether the output limit stopped the answer mid-sentence |

## Relations

| Concept | Cardinality | As |
| --- | --- | --- |
| Fence | one | bounded by |
| Cite | many | |
| Name | many | |
| Kept question | maybe one | kept as |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/chat-server/blob/main/lib/loop.mjs |
