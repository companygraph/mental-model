---
id: 01a10042-5dac-7cf8-b522-0814f72afc33
source: Local
kind: entity
refines: Check
---

# Check

> One named assertion a run makes over the whole instance, citing the one rule it holds part of, and reading what to hold each page to from the vendored schemas rather than from the checker's own lists.

## Attributes

| Attribute | Type | Description |
| --- | --- | --- |
| Name | string | What the check asserts, in a sentence: "required sections are present" |
| Rule | string | The rule in the conventions it holds part of, such as `R16` |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/lib/checks.mjs |
