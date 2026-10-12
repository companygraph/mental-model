---
id: 01a1312d-161d-7b5f-a34e-0cae94d0d90c
source: Local
kind: functional
modality: must
---

# A claim the evidence does not carry is marked before the answer ends

> After an answer's last sentence, each claim is read back against the tool answers that carried the entities it names, and every verdict reaches the page before the answer ends.

## Why

An answer can name the right entity and say something about it the entity does not bear out, and the visitor deciding which sentences to trust needs that shown where they read, not in a report later. A verdict that arrived after the answer closed would mark nothing.

## Fit criterion

Given a claim whose verdict is carried in part, with a probability above the deployment's threshold, the page underlines the sentence, a note on hover or focus says so, a line under the answer says one claim was marked, and the kept line counts it; given a judge that does not answer within the check's budget, the answer ends as it would have and the kept line carries no count.

## Applies to

| Type | Entity |
| --- | --- |
| feature | A chat answer marks the claims its evidence does not carry |

## References

| What | URL |
| --- | --- |
| The design, with what was measured | https://github.com/companygraph/chat-server/blob/main/docs/superpowers/specs/2026-09-26-the-answer-is-checked-design.md |
