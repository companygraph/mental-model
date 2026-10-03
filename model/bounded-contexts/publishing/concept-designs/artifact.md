---
id: 01a10042-5ac3-7831-b4d1-38cacb0d30d2
source: Local
kind: entity
---

# Artifact

> A committed file that holds one model as the parser read it at one pin's commit, which a stage page draws and an agent can fetch: the vocabulary, the example or the company.

## Attributes

| Attribute | Type | Description |
| --- | --- | --- |
| Name | string | `model`, `example` or `company`, which names the file and the page that draws it |
| Commit | commit hash | The commit it was built from, carried in the file |
| Repository | string | Where it came from, carried only by the one not drawn from the meta-model |
| Entities | list | Every entity read, each with its id, type, name and path |
| Edges | list | Every reference drawn, each with the field or column that drew it |

## Relations

| Concept | Cardinality | As |
| --- | --- | --- |
| Pin | one | drawn from |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/companygraph.github.io/blob/main/build/build.mjs |
