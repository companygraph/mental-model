---
id: 01a1312c-8b85-7881-89ea-ded665d4a36f
source: Local
kind: constraint
modality: must
follows:
  - Nothing claims what the model does not hold
realization: Released
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

## Realization

The server answers only from a snapshot of the model at one commit and carries the commit on every answer; its tools have no write path and add no inference. The chat gets only the host's tools, is told to state only what a tool returned and to say where the model does not say, and where a deployment checks its answers marks a claim the tool answers do not carry; the model page and the example page are drawn from the model's own data and held to it by the site's `pages:check` and `build:check`. A test checks that every server answer names a commit. Nothing checks that the same question put to the owner and to an agent gives agreeing answers, and the chat's answer is the language model's wording, held to the model by a prompt and a mark, not by construction.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `test/server.test.mjs` | satisfies | https://github.com/companygraph/mcp-server/blob/v0.69.0/test/server.test.mjs |
| `lib/prompt.mjs` | satisfies | https://github.com/companygraph/chat-server/blob/v0.38.3/lib/prompt.mjs |
| `.github/workflows/ci.yml` | satisfies | https://github.com/companygraph/companygraph.github.io/blob/3f8e4a25f599cc0e3c77cce8cce17e585d7a6b0e/.github/workflows/ci.yml |

## References

| What | URL |
| --- | --- |
| The strategy that rules out a paraphrase and an inferred answer | https://github.com/companygraph/mental-model/blob/main/model/strategies/read-only-server-strategy.md |
