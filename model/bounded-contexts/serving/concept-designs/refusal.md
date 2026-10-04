---
id: 01a10042-5bf0-71af-a0f1-3f35a8ae8355
source: Local
kind: value object
---

# Refusal

> A question the server declines to answer, said twice: as a sentence for a reader and as a code from a closed list for a program, with the facts the sentence names under keys the code fixes.

## Attributes

| Attribute | Term | Type | Many | Description |
| --- | --- | --- | --- | --- |
| Code | | string | | One of the closed list a client may branch on, such as `ambiguous_name` or `invalid_cursor` |
| Message | | string | | The sentence for a reader |
| Rule | | string | | The convention the refusal rests on, where one does |
| Details | | map | | The facts the sentence names, such as the candidates an ambiguous name holds, each a string |
| Provenance | Provenance | | | The snapshot that refused |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/mcp-server/blob/main/lib/errors.mjs |
