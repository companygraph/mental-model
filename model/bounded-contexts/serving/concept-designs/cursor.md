---
id: 01a10042-5c20-7bc7-bfd7-dcd3fa3db96f
source: Local
kind: value object
---

# Cursor

> An opaque token that says where the next page of a list starts and which commit's list it belongs to. It is good only against the snapshot that wrote it and only with the arguments of the call that wrote it.

## Attributes

| Attribute | Type | Description |
| --- | --- | --- |
| Offset | number | Where the next page starts in the list's fixed order |
| Commit | commit hash | The commit of the snapshot that wrote it |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/mcp-server/blob/main/lib/paging.mjs |
