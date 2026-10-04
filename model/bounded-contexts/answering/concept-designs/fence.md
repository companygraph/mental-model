---
id: 01a10042-6035-7e65-bb4e-5cc2bb44b816
source: Local
kind: value object
---

# Fence

> The bounds every message is answered within, which make the cost of one message a known ceiling whatever the visitor sends. A bound tightened is a break of the interface.

## Attributes

| Attribute | Term | Type | Many | Description |
| --- | --- | --- | --- | --- |
| Message length | | number | | The longest a visitor's turn may be, after trimming, in characters |
| Turns | | number | | How many of the last turns reach the model |
| Rounds | | number | | How many tool rounds a message may take before its last request |
| Tool answer length | | number | | How much of one tool's answer the model reads, in characters |
| Output | | number | | How much the model may write in one request, in tokens |
| Names | | number | | How many names one message may give the page |
| Messages an hour | | number | | How many messages one address may send in an hour |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/chat-server/blob/main/lib/shape.mjs |
| The interface | https://github.com/companygraph/chat-server/blob/main/docs/INTERFACE.md |
