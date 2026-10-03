---
id: 01a10042-5e42-7015-910a-80f55a8fce71
source: Local
emitted-by: Check run
---

# Run refused

> A checker declined to read an instance because it is not the release the instance named, the instance vendors a newer core or it takes a pack the checker does not ship, and it said which pin to move.

## Payload

| Attribute | Type | Description |
| --- | --- | --- |
| Tooling pin | Tooling pin | What the manifest names |
| Checker release | version | The release that refused |
| Reason | string | The pin or pack that disagreed, and what to move |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/bin/check-instance.mjs |
