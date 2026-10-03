---
id: 01a10042-6283-7797-9680-ea2fbc247024
source: Local
emitted-by: Manifest
---

# Instance moved to a release

> An instance's vendored files, manifest and workflow ref moved to another release together, and the files it owns but lacked were given to it.

## Payload

| Attribute | Type | Description |
| --- | --- | --- |
| From | version | The core version the manifest named before |
| To | version | The core version it names now |
| Written | list of Vendored file | The files the release changed or added |
| Removed | list of string | The paths the release no longer ships |
| Given | list of string | The repository's own files written because it had none |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/lib/plan.mjs |
