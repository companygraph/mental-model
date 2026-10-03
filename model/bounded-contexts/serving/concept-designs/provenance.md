---
id: 01a10042-5bbc-7adf-b3a9-9ce371c484b5
source: Local
kind: value object
---

# Provenance

> Where an answer came from: the commit and repository the model was read at and the core and parser releases it was read with. Every answer and every refusal carries it, under `model`, so an answer can be checked against the same bytes later.

## Attributes

| Attribute | Type | Description |
| --- | --- | --- |
| Commit | commit hash | The commit the snapshot was taken at; empty for a working tree |
| Repository | string | The repository it was read from; empty for a working tree |
| Core version | version | The core release the instance vendors |
| Parser | version | The release of the parser that drew the graph |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/mcp-server/blob/main/lib/model.mjs |
