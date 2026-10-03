---
id: 01a10042-5cb5-7e3d-8873-9fe1e820d36e
source: Local
kind: value object
---

# List page

> One stretch of a long list as one answer hands it out: how many entries the list holds after its filters, how many came back, whether more follow and the cursor to the next. A list page is a part of an answer, never an entity's page in the model.

## Attributes

| Attribute | Type | Description |
| --- | --- | --- |
| Total | number | The entries the list holds after its filters |
| Returned | number | The entries this page holds |
| Has more | boolean | Whether entries follow this page |
| Next cursor | Cursor | Where the next page starts; empty when none follows |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/mcp-server/blob/main/lib/paging.mjs |
