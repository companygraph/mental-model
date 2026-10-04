---
id: 01a10042-5e73-7117-9b8c-8bf69d19fe2a
source: Local
emitted-by: Check run
---

# Instance checked

> An instance was read whole against the rules it vendored, and the run reported every finding, every type it could not check and the writing rules it left to the agent pass.

## Payload

| Attribute | Term | Type | Many | Description |
| --- | --- | --- | --- | --- |
| Findings | Finding | | yes | Every finding of the run, none when it passed |
| Not checked | | string | yes | The types the vendored units carry no schema for |
| Core version | | version | | The core release the instance was held to |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/bin/check-instance.mjs |
