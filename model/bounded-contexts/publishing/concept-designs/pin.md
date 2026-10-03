---
id: 01a10042-5a60-7787-8968-300bd59baafb
source: Local
kind: value object
refines: Pin
---

# Pin

> One repository and the commit of it a site draws its artifacts from, named once for the site and moved only when someone commits a new one.

## Attributes

| Attribute | Type | Description |
| --- | --- | --- |
| Name | string | What the site calls it, `meta-model` or `mental-model` |
| Repository | string | The repository it points into |
| Commit | commit hash | The commit drawn |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/companygraph.github.io/blob/main/source.json |
| Implementation | https://github.com/companygraph/companygraph.github.io/blob/main/pin-check.mjs |
