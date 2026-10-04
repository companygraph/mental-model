---
id: 01a10042-5d47-70e6-a2e7-84b1a2ea8d2f
source: Local
kind: value object
---

# Vocabulary

> Every type an instance is held to: core's, then the types of each pack it took, each with the unit it belongs to and the vendored folder its schema is read from.

## Attributes

| Attribute | Term | Type | Many | Description |
| --- | --- | --- | --- | --- |
| Types | | string | yes | Each type with its folder, its owner where it is owned, and where it carries labels |
| Units | | string | yes | Core and each pack the manifest names, each with the folder it is vendored in |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/lib/checks.mjs |
