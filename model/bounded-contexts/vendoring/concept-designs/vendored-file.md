---
id: 01a10042-618d-798e-bbd9-e00c70bd0dad
source: Local
kind: value object
---

# Vendored file

> One file the tooling wrote into a repository and owns there, a schema of core or of a pack or one of the agent's skills, known by its path and the hash of the text it was written with. A file of the same path with any other text is an edit, not the vendored file.

## Attributes

| Attribute | Term | Type | Many | Description |
| --- | --- | --- | --- | --- |
| Path | | string | | Where it sits, plain and relative, under the units folder or the skills folder |
| Hash | | string | | `sha256:` and the digest of its text, line ends read as `\n` |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/lib/plan.mjs |
