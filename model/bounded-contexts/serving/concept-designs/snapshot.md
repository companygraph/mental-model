---
id: 01a10042-5b8a-71bb-bed7-368901f26aea
source: Local
kind: entity
---

# Snapshot

> The graph of one instance, taken once at one commit together with the vocabulary it was read against, which a deployment serves unchanged for as long as it runs. It is named by its commit, and a working tree with uncommitted changes is served as having none.

## Attributes

| Attribute | Term | Type | Many | Description |
| --- | --- | --- | --- | --- |
| Provenance | Provenance | | | Where every answer from it came from |
| Entities | Entity | | yes | Every entity of the graph, each with its page as written |
| Edges | Edge | | yes | The graph's edges, untouched |
| Schemas | Schema | | yes | The types the instance declares and what each declares about the others |
| Rules | Rule | | yes | The conventions of the core the instance vendors, where it ships them |
| Checks | Check | | yes | The checks the instance's own gate runs, listed and never run here |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/mcp-server/blob/main/lib/snapshot.mjs |
