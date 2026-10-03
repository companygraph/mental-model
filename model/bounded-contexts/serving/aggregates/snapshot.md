---
id: 01a10042-5b58-7499-b4a6-d415f9bf7484
source: Local
root: Snapshot
members:
  - Provenance
decisions:
  - The server only reads, and answers at one named commit
---

# Snapshot

> Every answer a deployment gives is read from one snapshot that no question changes, and says which commit that snapshot was taken at.

## Invariants

| Label | Invariant |
| --- | --- |
| INV-S1 | Every answer and every refusal carries the snapshot's provenance. |
| INV-S2 | No tool changes the snapshot; what a search derives from it is kept beside it, never in it. |
| INV-S3 | A snapshot taken from a working tree with uncommitted changes names no commit, never the last one. |
| INV-S4 | Every paged list has one fixed order, so following the cursors from the first page returns each entry exactly once. |
| INV-S5 | A cursor is honored only by a snapshot of the commit that wrote it; any other is refused as `invalid_cursor`. |
| INV-S6 | A limit outside the allowed range is served at the nearest bound and never refused. |
| INV-S7 | Every refusal carries a code from the closed list; a code outside it cannot be raised. |
| INV-S8 | A name that two entities of one type hold is refused as `ambiguous_name` with every candidate's id, never answered with one of them. |

## Handled commands

| Command | Description |
| --- | --- |
| Take a snapshot | Reads an instance at a commit, from a repository or a working tree, against the core and packs it vendors; refuses with one line when the instance cannot be read |
| Answer a tool call | Holds the arguments to the tool's input schema and answers from the snapshot, or refuses with a code |
| Hand out the next page | Answers the page a cursor points at, or refuses a cursor this server did not write or wrote for another commit |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/mcp-server/blob/main/lib/tools.mjs |
| Implementation | https://github.com/companygraph/mcp-server/blob/main/lib/paging.mjs |
