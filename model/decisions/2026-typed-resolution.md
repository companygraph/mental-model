---
source: Local
decided: 2026-09-15
kind: Vocabulary
status: Standing
by: Owner
---

# A reference resolves by its declared type, never by name alone

> A tool resolves a reference by the type its schema declares and the name written, looks in no other type, and reports a name that exists only under another type as unresolvable.

## The question

What a tool does with a name that exists under two types, which a company of one forces, because the company and the only person in it are called the same thing. It had to be decided in September 2026, when the parser refused such a name as ambiguous and the reference instance could not be served.

## Alternatives

| Option | Why not |
| --- | --- |
| The first match across types | Which entity a reference reaches would depend on the order the folders were walked, and a string field whose value happened to be a canonical name would draw an edge nobody declared. |
| The nearest folder | It resolves by where a file happens to sit, which R3 forbids a reference to depend on, and moves the edge when the file moves. |

## Why

Every schema already declares its references as `ref → <type>`, so a reference carries a type as well as a name, and the pair is what resolves. A name unique across the whole instance would have forced the company or the person to be called something nobody calls it, and the graph would then describe a naming workaround rather than the company.

## Consequences

A name that exists only under another type is unresolvable, not ambiguous, and the error says which type was searched; the parser reads the type once and knows for every page which fields become edges. Every consumer re-pinned. What it gave up is the convenience of a bare name that means one thing everywhere.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| concept | Reference | | changed it |
| concept | Canonical name | | changed it |

## References

| What | URL |
| --- | --- |
| The specification | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-09-15-typed-resolution-design.md |
