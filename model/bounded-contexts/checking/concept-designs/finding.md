---
id: 01a10042-5de0-7bb8-883f-df40c304648e
source: Local
kind: value object
---

# Finding

> One thing a check found wrong, said as a sentence that names the file it is in and, where the check knows it, the schema or rule it breaks. Two findings with the same words are the same finding.

## Attributes

| Attribute | Type | Description |
| --- | --- | --- |
| Where | string | The path of the page, schema or vendored file the finding is about |
| What | string | What is wrong there, and what the schema permits or requires |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/lib/checks.mjs |
