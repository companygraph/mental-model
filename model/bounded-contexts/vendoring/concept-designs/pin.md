---
id: 01a10042-6222-7f6e-aff5-871d118ed475
source: Local
kind: value object
refines: Pin
---

# Pin

> One line in one file of a repository that takes another repository's tag or commit, declared in its `pins.json` or found where such lines are kept.

## Attributes

| Attribute | Term | Type | Many | Description |
| --- | --- | --- | --- | --- |
| Kind | | string | | How the line is read and whether it names a tag or a commit: `core-release`, `npm-tag`, `source-commit`, `contract-commit` or one of the family's own |
| File | | string | | The file the line is in |
| Repository | | string | | The upstream, as `owner/repository` |
| Declared | | boolean | | Whether `pins.json` names it, or it was only found |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/lib/pins.mjs |
