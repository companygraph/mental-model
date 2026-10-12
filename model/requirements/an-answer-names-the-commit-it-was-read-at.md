---
id: 01a1312c-9a9a-739b-917c-93031643590f
source: Local
kind: functional
modality: must
---

# An answer names the commit it was read at

> Every answer a surface gives from the model, a tool's, a chat's or a page's, names the commit of the model it was read at.

## Why

An answer can be checked against the same bytes later only when it says which bytes, and two answers given a week apart can be told apart only by the commit each names. Without it, a surface answers about a model's current state in general, which no one can hold it to.

## Fit criterion

Every tool answer of the server carries the commit under `model`; every chat answer names the commit each entity it cites was read at; and the model page draws the commit it was built at beside the figure.

## Applies to

| Type | Entity |
| --- | --- |
| feature | An agent reads the model |
| feature | A visitor asks the model |
| feature | The vocabulary on the web |

## References

| What | URL |
| --- | --- |
| The server's interface | https://github.com/companygraph/mcp-server/blob/main/docs/INTERFACE.md |
