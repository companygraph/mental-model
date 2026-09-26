---
source: Local
decided: 2026-09-16
kind: Architecture
status: Standing
by: Owner
upholds:
  - Run on what we publish
  - Adoption is not taxed
---

# The server only reads, and answers at one named commit

> An agent reaches a company's model through a server that reads it, answers every question at the commit it was read at, and adds nothing of its own.

## The question

What an agent may do to a company's model through the server, and how an answer can be checked later. It had to be decided when the server was designed, in September 2026, because a write path or a retrieval index would have shaped every tool on it.

## Alternatives

| Option | Why not |
| --- | --- |
| A write path | A company would have to decide whether to trust an agent with its model, and no company should have to decide that to adopt one. |
| An embedding index as the way in | A retrieval layer answers with a paraphrase, and a paraphrase cannot be held to the evidence the model attached to the claim. |

## Why

Every answer names the commit it was read at, so an answer can be checked against the same bytes later and two answers a week apart can be told apart. The tools are the vocabulary's own questions, which types a company declares, what one entity says, what evidence a claim rests on, so an agent asks the model the way the model is shaped rather than searching its text and hoping.

## Consequences

No answer about a model's current state in general, no reasoning the server does that the model cannot show, and nothing summarized away: where a claim has no evidence the answer says so. A company runs the server in its own cloud project from the parts we publish. What has to stay true is that the same question put to the person who runs the company and to the agent gets the same answer, followable to the page.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| strategy | Read-Only Server Strategy | | made it |

## References

| What | URL |
| --- | --- |
| The server | https://github.com/companygraph/mcp-server |
