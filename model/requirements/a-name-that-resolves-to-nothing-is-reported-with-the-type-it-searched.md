---
id: 01a1312e-00d6-7ac7-b6a7-49be23dc9ce9
source: Local
kind: functional
modality: must
---

# A name that resolves to nothing is reported with the type it searched

> The check reads every name a schema declares as a reference, and reports each one that resolves to nothing, with the type the declaration names and where the name was written.

## Why

A name resolves by the type its declaration names and never by a search over every type, so a writer told only that a name is unknown would look in the wrong folder; the type searched is what sends them to the right one.

## Fit criterion

A name that exists nowhere fails the page, saying what the column or field is declared to reference and that it names no entity; a name that exists under another type fails saying which type it is an entity of, and is never resolved there; and a name inside an owner resolves within that owner alone.

## Applies to

| Type | Entity |
| --- | --- |
| feature | Checks an instance runs |

## References

| What | URL |
| --- | --- |
| The rules every page obeys | https://github.com/companygraph/meta-model/blob/main/core/CONVENTIONS.md |
