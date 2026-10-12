---
id: 01a1312d-73b9-71de-84f0-e15974164afa
source: Local
kind: functional
modality: must
---

# A list arrives in pages that neither repeat nor skip

> A list of any length is answered a page at a time, and an agent that follows the cursor with the same arguments receives every result exactly once, in one order, every page naming the same commit.

## Why

An agent passing a list on to a visitor cannot check it for gaps or doubles; the server has to make both impossible, and a page from another commit would mix two models into one list.

## Fit criterion

A search whose results run past one page, followed to its end, yields every result exactly once in one order with every page naming the same commit; and a limit of zero is answered with one entry and a page that says one was returned.

## Applies to

| Type | Entity |
| --- | --- |
| use-case | Walk a long list a page at a time |

## References

| What | URL |
| --- | --- |
| The interface, Paging | https://github.com/companygraph/mcp-server/blob/main/docs/INTERFACE.md#paging |
