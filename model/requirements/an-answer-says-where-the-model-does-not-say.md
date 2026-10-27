---
id: 01a1312d-0688-7aba-a96a-fcbd55585385
source: Local
kind: functional
modality: must
realization: Released
---

# An answer says where the model does not say

> Where the tools returned nothing on a matter, the answer says that the model does not say, rather than filling the gap with something plausible.

## Why

A visitor cannot tell a claim the model carries from one the agent made up unless the answer draws the line itself; a gap filled with something plausible is the one kind of wrong answer that reads exactly like a right one.

## Fit criterion

Given a question the tools returned nothing for, the answer says the model does not say; and a claim that the model holds nothing on a matter, in a message where a tool returned rows, is read back as withheld and counts as not carried.

## Applies to

| Type | Entity |
| --- | --- |
| use-case | Ask the company a question |

## Realization

The prompt tells the model that where the tools do not say, it says the model does not say, and the last request repeats it. The answer check reads a claim that the model holds nothing as `says-nothing` where every tool call found nothing and as `withheld` where a call found rows; `withheld` counts as not carried, and a test checks both verdicts and that `withheld` is unsupported. Whether an answer to a question the tools returned nothing for really says so is the model's behavior and no test observes it.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `test/verdict.test.mjs` | satisfies | https://github.com/companygraph/chat-server/blob/v0.38.3/test/verdict.test.mjs |
| `lib/model.mjs` | satisfies | https://github.com/companygraph/chat-server/blob/v0.38.3/lib/model.mjs |

## References

| What | URL |
| --- | --- |
| The design of one message answered | https://github.com/companygraph/chat-server/blob/main/docs/design/answering.md |
