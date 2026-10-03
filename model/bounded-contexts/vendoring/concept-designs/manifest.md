---
id: 01a10042-61bc-7bdb-b955-d6d0874c67ac
source: Local
kind: entity
---

# Manifest

> The record a repository keeps of what it took from the meta-model: the release it runs, the core it vendors with where that came from and every file the tooling wrote and still owns. A manifest that names no core is a repository that took the machinery and holds no model.

## Attributes

| Attribute | Type | Description |
| --- | --- | --- |
| Tooling | version | The release whose checker the repository's workflow runs, and the one every command compares itself against |
| Core version | version | The version of the core vendored; it may lag the tooling and never lead it |
| Core shape | number | The shape of that core, as its own manifest gives it |
| Core source | string | `bundled` for the core inside the release that ran, or `fetched:<tag>` for one fetched by tag |
| Units | string | The folder core and the packs are vendored under, `meta` unless named |
| Exclude | list of string | The paths the form leaves out |

## Relations

| Concept | Cardinality | As |
| --- | --- | --- |
| Unit | many | vendored |
| Vendored file | many | owned |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/lib/instance-files.mjs |
