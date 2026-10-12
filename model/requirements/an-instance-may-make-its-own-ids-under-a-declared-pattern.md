---
id: 01a1312c-ba31-768b-ab88-cf336c1c4884
source: Local
kind: functional
modality: may
---

# An instance may make its own ids under a declared pattern

> An instance may declare a pattern its ids follow instead of the tooling's own format, and then the tooling only checks the ids and never stamps one.

## Why

A company that already issues identifiers, in a register or a ticket system, keeps them rather than carrying a second id beside its own; a tooling that stamped its own format over them would make every page carry two.

## Fit criterion

With a pattern declared in the identifier page, the check holds every id to the pattern, and the backfill command refuses whole rather than writing an id of the tooling's own format.

## Applies to

| Type | Entity |
| --- | --- |
| feature | An instance is made and kept from one command |

## References

| What | URL |
| --- | --- |
| The identifier schema | https://github.com/companygraph/meta-model/blob/main/core/identifier-schema.md |
