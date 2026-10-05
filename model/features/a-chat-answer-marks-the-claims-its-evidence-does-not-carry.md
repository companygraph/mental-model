---
id: 01a10a8a-fb15-798b-b3a3-6379060ee373
source: Local
products:
  - CompanyGraph Core
concepts:
  - Entity
  - Reference
---

# A chat answer marks the claims its evidence does not carry

> Someone reading an answer from a company's model sees which of its sentences the entities it names do not bear out, before deciding which of them to trust.

## Description

Each claim of an answer, a sentence, a list item or a table row, is read back against the text of the tool answers that carried the entities it names, exactly as the model was given it, by a decision model outside the machine that picks a verdict with a probability and writes nothing. Where a deployment checks its answers, the chat marks a claim the evidence carries only in part, or not at all, once the answer is drawn, with a note saying which, and a line under the answer says how many it marked. It marks only above a probability measured on real answers, marks nothing in an answer written in German until German is measured on its own, and marks nothing where the check could not run. It stops at the mark: it changes no answer, it says whether a claim keeps to what the model says and never whether the model is right, and every checked answer is counted in the week's report whether it was marked or not.

## References

| What | URL |
| --- | --- |
| The design of the check, and what was measured before it marked anything | https://github.com/companygraph/chat-server/blob/main/docs/superpowers/specs/2026-09-26-the-answer-is-checked-design.md |
| The event the chat sends with each claim's verdict | https://github.com/companygraph/chat-server/blob/main/docs/INTERFACE.md |
| The code that marks a claim where the visitor reads it | https://github.com/robertblust/design/blob/main/assets/chat.js |
