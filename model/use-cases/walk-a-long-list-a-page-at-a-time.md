---
id: 01a1312c-7bf1-7220-aac8-2909c906829e
source: Local
level: subfunction
scope: component
primary-actor: Agent
realization: Released end to end
---

# Walk a long list a page at a time

> An agent takes a list of any length in pages that neither repeat nor skip, and is told with a code, not left to guess, when its place in the list no longer holds.

## Stakeholders and interests

| Stakeholder | Interest |
| --- | --- |
| Agent | Every result once, in one order, and a code where its cursor no longer holds |
| Visitor | Nothing missing from what the agent passes on |
| Owner | No answer that mixes two commits |

## Main success scenario

| Step | Actor | Action |
| --- | --- | --- |
| 1 | Agent | Asks for the list's first page with its arguments |
| 2 | System | Answers one page, with the cursor to the next, whether more follow, and the commit |
| 3 | Agent | Follows the cursor with the same arguments while more follow |
| 4 | System | Answers each later page naming the same commit, every result exactly once, in one order |

## Extensions

| Step | Condition | Handling |
| --- | --- | --- |
| 1a | The limit asked for is out of range, zero | One entry comes back and the page says one was returned, so the agent sees what it got rather than a refusal |
| 3a | The cursor was written before the deployment moved to a later commit | The call is refused with the code for an invalid cursor and the reason that it is from another commit, the refusal names the commit now served, and the agent starts again from the first page |
| 3b | The cursor is one the server did not write | The call is refused with the code for an invalid cursor and the reason that it is malformed, and the sentence says to leave it out to start from the first page |

## Minimal guarantees

- No page mixes two commits.
- A cursor that no longer holds is refused with a code, never served from a guess.

## Success guarantees

- Every result arrived exactly once, in one order, at one commit.

## Realization

mcp-server v0.69.0 pages every list tool (`list_entities`, `search`, `list_references`) with a default of 50, a maximum of 200, and a limit outside the range served at the nearest bound, so a limit of zero returns one entry and the page says so (1a). Each page carries `total`, `returned`, `hasMore`, `nextCursor` and the commit under `model` (steps 2 and 4). A cursor written for another commit is refused as `invalid_cursor` with the reason `other_commit`, and the refusal carries the served commit under `model` (3a); a cursor the server did not write is refused with the reason `malformed` and a sentence that says to leave it out (3b). `test/contract.test.mjs` walks each of the three tools at page sizes 2 and 200 through an MCP client, expects the same list in both and nothing twice, and `test/paging.test.mjs` tests the refusals. One gap in the page's second guarantee: a cursor sent back with other arguments than the call that made it is not detected, which `docs/INTERFACE.md` says.

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
