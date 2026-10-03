---
id: 01a10042-5d7b-7cad-9ed5-b55e738c8785
source: Local
kind: value object
refines: Pin
---

# Tooling pin

> The release of the checker an instance's manifest names, which its workflow line calls by the same tag; a run by any other release refuses rather than hold the instance to rules nobody chose.

## Attributes

| Attribute | Type | Description |
| --- | --- | --- |
| Tooling | version | The release the manifest's `tooling` names |
| Core version | version | The core release the manifest says was vendored, which may be older than the tooling and never newer |
| Packs | list of string | The packs the manifest names |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/bin/check-instance.mjs |
