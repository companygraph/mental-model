---
id: 01a10042-6283-7797-9680-ea2fbc247024
source: Local
emitted-by: Manifest
---

# Instance moved to a release

> An instance's vendored files, manifest and workflow ref moved to another release together, and the files it owns but lacked were given to it.

## Payload

| Attribute | Term | Type | Many | Description |
| --- | --- | --- | --- | --- |
| From | | version | | The core version the manifest named before |
| To | | version | | The core version it names now |
| Written | Vendored file | | yes | The files the release changed or added |
| Removed | | string | yes | The paths the release no longer ships |
| Given | | string | yes | The repository's own files written because it had none |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/lib/plan.mjs |
