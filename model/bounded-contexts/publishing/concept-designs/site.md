---
id: 01a10042-59cd-7c23-825f-8d0e956f2f2d
source: Local
kind: entity
---

# Site

> A website that draws a model: its origin, the pins it draws from and everything it publishes from them, held together so nothing on it is drawn at a commit its pins do not name.

## Attributes

| Attribute | Type | Description |
| --- | --- | --- |
| Origin | URL | The scheme and host every address it publishes starts with |

## Relations

| Concept | Cardinality | As |
| --- | --- | --- |
| Pin | one to many | |
| Artifact | one to many | |
| Stage page | many | |
| Derived region | many | |
| Share card | many | |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/companygraph.github.io/blob/main/source.json |
