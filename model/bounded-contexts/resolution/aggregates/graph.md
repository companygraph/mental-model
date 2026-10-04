---
id: 01a0faae-d24f-7363-b997-383d2b553a2e
source: Local
root: Graph
members:
  - Edge
  - Scope
decisions:
  - A reference resolves by its declared type, never by name alone
  - Every entity carries an id that outlives its name
---

# Graph

> Every edge of an instance's graph joins two entities that exist in it, each found by the type and owner its declaration names.

## Invariants

| Label | Invariant |
| --- | --- |
| INV-R1 | Every edge runs between two entities of the graph; a name that resolves to nothing stops the read, and no edge points nowhere. |
| INV-R2 | A written name is looked for only among the type its declaration names, so a name that exists only under another type is unresolvable, never ambiguous. |
| INV-R3 | A name of an owned type is looked for only within its owner, so two owners may each hold a page of that name. |
| INV-R4 | Within one scope no two entities share a canonical name. |
| INV-R5 | A qualifier must resolve but draws no edge; its value describes the edge its row draws. |
| INV-R6 | A `ref?` that names nothing stays a fact and draws no edge. |
| INV-R7 | An edge joins entities by id, so renaming a page keeps every edge to it. |

## Handled commands

| Command | Emits | When | Description |
| --- | --- | --- | --- |
| Read an instance | | | Reads every page against the schemas the instance vendors and draws the graph, or refuses at the first name that resolves to nothing |
| Resolve a row | | | Finds what one table row's Type, Entity and Owner cells name, for an editor completing a cell as it is written |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/lib/instance.mjs |
