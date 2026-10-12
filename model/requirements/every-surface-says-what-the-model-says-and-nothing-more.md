---
id: 01a1312c-8b85-7881-89ea-ded665d4a36f
source: Local
kind: constraint
modality: must
follows:
  - Nothing claims what the model does not hold
---

# Every surface says what the model says and nothing more

> Every surface that derives from a company's model, a page, a server's answer or a chat's, reports what the model says at one commit and adds no reasoning the model cannot show.

## Why

A visitor, a search engine and an agent should reach the same answer whoever asks, and that holds only when every surface derives from the one model the company keeps. A retrieval layer answers with a paraphrase that cannot be held to the evidence the model attached to the claim, and an inferred answer, however useful, is one the company cannot be held to.

## Fit criterion

The same question put to the person who runs the company and to an agent reading its model gives two answers that agree, with the agent's followable to the page it came from; and the count of answers that name no commit is zero.

## Applies to

| Type | Entity |
| --- | --- |
| product | CompanyGraph Core |

## References

| What | URL |
| --- | --- |
| The strategy that rules out a paraphrase and an inferred answer | https://github.com/companygraph/mental-model/blob/main/model/strategies/read-only-server-strategy.md |
