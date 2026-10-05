---
id: 01a10a8f-21c3-7313-8edb-6518d09a0e5f
source: Local
kind: value object
---

# Claim

> One sentence, list item or table row of an answer, with the entities it names and the verdict on whether the tool answers that carried them say what it says.

## Attributes

| Attribute | Term | Type | Many | Description |
| --- | --- | --- | --- | --- |
| From | | number | | Where it starts in the answer's text, counted over the answer as it streamed |
| To | | number | | Where it ends |
| Names | | id | yes | The entities whose titles it writes, by their ids |
| Verdict | | string | | `supported`, `partial`, `contradicted`, `absent`, `says-nothing`, `withheld`, `unnamed` or `unsourced` |
| Probability | | number | | The probability the judge gave the verdict, empty where no judge was asked |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/chat-server/blob/main/lib/verdict.mjs |
