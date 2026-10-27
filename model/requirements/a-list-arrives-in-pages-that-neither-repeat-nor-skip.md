---
id: 01a1312d-73b9-71de-84f0-e15974164afa
source: Local
kind: functional
modality: must
realization: Verified
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

## Realization

A list is answered a page at a time with a default of 50 and a maximum of 200; the cursor is the offset plus the commit, so a cursor from another commit is refused and a walk cannot mix two models. Lists have a fixed order within a snapshot. A contract test walks `list_entities`, `search` and `list_references` at page sizes 2 and 200, follows `nextCursor` while `hasMore`, and checks both walks yield the same list with no id twice. A unit test walks a list of 137 in pages of 30 and gets the list once. A limit of zero is raised to one and the page says `returned: 1`. That every page of a walk names the same commit is not asserted in one test; it follows from the cursor's commit check, which a test covers.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `test/contract.test.mjs` | verifies | https://github.com/companygraph/mcp-server/blob/v0.69.0/test/contract.test.mjs |
| `test/paging.test.mjs` | verifies | https://github.com/companygraph/mcp-server/blob/v0.69.0/test/paging.test.mjs |
| `lib/paging.mjs` | satisfies | https://github.com/companygraph/mcp-server/blob/v0.69.0/lib/paging.mjs |

## References

| What | URL |
| --- | --- |
| The interface, Paging | https://github.com/companygraph/mcp-server/blob/main/docs/INTERFACE.md#paging |
