---
id: 01a10042-5a2e-7213-962a-700bb00a0163
source: Local
kind: entity
---

# Stage page

> A page that names one artifact and draws it in the browser as a graph to walk, one focused entity at a time, with the commit it was drawn at beside the figure.

## Attributes

| Attribute | Term | Type | Many | Description |
| --- | --- | --- | --- | --- |
| Address | | string | | Where the page is: `/model/`, `/example/` or the landing page |
| Source folder | | string | | The folder of the repository the artifact was read from, which the source link names |

## Relations

| Concept | Cardinality | As |
| --- | --- | --- |
| Artifact | one | draws |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/companygraph.github.io/blob/main/stage.js |
| Implementation | https://github.com/companygraph/companygraph.github.io/blob/main/model/index.html |
