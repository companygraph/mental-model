---
id: 01a0faaa-5d02-71db-bcdb-f672c4324bee
source: Local
classification: core
realizes:
  - Core
decisions:
  - A reference resolves by its declared type, never by name alone
---

# Resolution

> Turns the names a page writes into the edges of the graph, by the type each schema declares and the owner a row names. Whether a page has the shape its schema asks for is left to the checks.

## Responsibilities

- Find the entity a written name means, looking only among the type the schema declares for that field or column
- Look for an owned entity only inside the owner its row names, so two owners can each have a page of the same name
- Report a name that exists only under another type as unresolvable, and say which type was searched
- Tell the fields and columns that draw an edge from the ones that only qualify a row
- Record on every edge the field or column that drew it, so a reader can see why two entities are joined

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/lib/instance.mjs |
| The specification | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-09-15-typed-resolution-design.md |
