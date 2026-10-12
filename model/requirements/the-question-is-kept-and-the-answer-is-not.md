---
id: 01a1312d-2629-72e5-9208-31b5c5db8047
source: Local
kind: constraint
modality: must
---

# The question is kept and the answer is not

> A chat keeps of each message one line, the question itself and whether the model could answer it, never with an address and never past ninety days, and keeps no answer.

## Why

The one quantity the company watches is whether an answer rested on the model, and that is read from the question and the entities cited, not from the answer's text; an answer kept would be a record of a conversation the visitor was promised lives in their tab and ends with it.

## Fit criterion

The kept line holds the question, its language, the entities the answer cited, how many tool calls were made and how many found nothing, and whether the fence refused, and no field holds the answer or an address; a line older than ninety days is gone.

## Applies to

| Type | Entity |
| --- | --- |
| feature | A visitor asks the model |

## References

| What | URL |
| --- | --- |
| The interface, with the kept line's fields | https://github.com/companygraph/chat-server/blob/main/docs/INTERFACE.md |
