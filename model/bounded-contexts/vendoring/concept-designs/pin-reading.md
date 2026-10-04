---
id: 01a10042-61ef-7eb4-9217-34bff7eca832
source: Local
kind: value object
---

# Pin reading

> What one pin says against what its upstream offers at the moment it is asked. A reading of behind is a fact about the upstream, not a fault: it is intent until the owner calls it drift.

## Attributes

| Attribute | Term | Type | Many | Description |
| --- | --- | --- | --- | --- |
| Status | | string | | `current`, `behind`, `unknown` where the upstream cannot be reached, `unmanaged` for a line no declaration names, `missing` for a declaration that names no line or `family` for a kind the family's own resync reads |
| Pinned | | string | yes | The tags or commits the line names |
| Newest | | string | | The highest version tag, or the upstream's head commit, as the upstream offers it now; said only when the pin is behind |

## Relations

| Concept | Cardinality | As |
| --- | --- | --- |
| Pin | one | read |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/lib/pins.mjs |
