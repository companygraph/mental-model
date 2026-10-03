---
id: 01a10042-6442-732f-9e77-99628776dbd9
source: Local
refines: An agent reads the model
contexts:
  - Serving
decisions:
  - The server only reads, and answers at one named commit
---

# A long list is walked a page at a time

> An agent takes a list of any length in pages that neither repeat nor skip, and is told with a code, not left to guess, when its place in the list no longer holds.

## Operational principle

An agent searches the model and gets the first page with a cursor; it sends the cursor back with the same arguments until no more pages follow, and holds every result once, each page naming the commit it came from.

## Scenarios

### SC-S1: A list walked to its end

Given a search whose results run past one page, when the agent follows `page.nextCursor` with the same arguments while `page.hasMore` holds, then every result arrives exactly once, in one order, and every page names the same commit.

### SC-S2: A limit out of range is served, not refused

Given a list call with a limit of 0, when it is answered, then one entry comes back and the page says one was returned, so the agent sees what it got rather than a refusal.

### SC-S3: A cursor from an earlier commit is refused

Given a cursor written before the deployment moved to a later commit, when the agent sends it, then the call is refused with the code `invalid_cursor` and the reason `other_commit`, the refusal names the commit now served, and the agent starts again from the first page.

### SC-S4: A cursor the server did not write is refused

Given a cursor the agent made up or cut short, when the agent sends it, then the call is refused with the code `invalid_cursor` and the reason `malformed`, and the sentence says to leave it out to start from the first page.

## Uses

| Type | Entity | Context |
| --- | --- | --- |
| concept-design | List page | Serving |
| concept-design | Cursor | Serving |
| concept-design | Refusal | Serving |
| concept-design | Provenance | Serving |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/mcp-server/blob/main/lib/paging.mjs |
| The interface, Paging | https://github.com/companygraph/mcp-server/blob/main/docs/INTERFACE.md#paging |
