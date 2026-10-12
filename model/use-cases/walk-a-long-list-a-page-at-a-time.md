---
id: 01a1312c-7bf1-7220-aac8-2909c906829e
source: Local
level: subfunction
scope: component
primary-actor: Agent
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

## References

| What | URL |
| --- | --- |
| The interface, Paging | https://github.com/companygraph/mcp-server/blob/main/docs/INTERFACE.md#paging |
