---
id: 01a10042-5e10-7ae1-a2a7-a6b0497dddd0
source: Local
kind: entity
---

# Check run

> One checking of an instance as it stands, by one release of the checker, against the core and packs that instance vendored: it either refuses before reading a page or reads them all and reports what it found.

## Attributes

| Attribute | Type | Description |
| --- | --- | --- |
| Checker release | version | The release doing the checking, which must be the one the tooling pin names |
| Core version | version | The core release the manifest says the instance vendored |
| Not checked | list of string | The types the vendored units carry no schema for |
| Outcome | string | Refused, passed or failed |

## Relations

| Concept | Cardinality | As |
| --- | --- | --- |
| Tooling pin | one | |
| Vocabulary | one | |
| Check | one to many | |
| Finding | many | |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/bin/check-instance.mjs |
