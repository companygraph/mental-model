---
id: 01a10042-599c-770a-a5e1-af7664d42cd7
source: Local
kind: value object
---

# Derived region

> A part of the site written from the artifacts and never by hand: a region inside a hand-written page, such as its JSON-LD graph, or a whole page, such as an entity's id page. It is rewritten whole, never edited.

## Attributes

| Attribute | Type | Description |
| --- | --- | --- |
| Page | string | The page it sits in, or is |
| Kind | string | What it is: a JSON-LD graph, the vision and values, a team board, the surfaces, the principles, an id page |

## Relations

| Concept | Cardinality | As |
| --- | --- | --- |
| Artifact | one to many | drawn from |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/companygraph.github.io/blob/main/build/pages.mjs |
| Implementation | https://github.com/companygraph/companygraph.github.io/blob/main/build/jsonld.mjs |
