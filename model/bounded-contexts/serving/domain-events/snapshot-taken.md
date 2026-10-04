---
id: 01a10042-5c84-7812-b049-8e153dc80fef
source: Local
emitted-by: Snapshot
---

# Snapshot taken

> An instance was read at a commit and written down as the snapshot a deployment will serve.

## Payload

| Attribute | Term | Type | Many | Description |
| --- | --- | --- | --- | --- |
| Provenance | Provenance | | | The commit, repository, core and parser it was taken with |
| Entities | | number | | How many entities it holds |
| Edges | | number | | How many edges it holds |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/mcp-server/blob/main/bin/snapshot.mjs |
