---
id: 01a1312d-54ac-7c7c-b554-5cb0398ec71d
source: Local
kind: functional
modality: must
realization: Released
---

# An answer rests only on what the host's tools returned

> The model that writes an answer may only ask the host's tools, and every claim in the answer names the entity a tool returned it from in that conversation.

## Why

An agent answering as well as the person who runs the company means every claim can be followed to the page it came from, and that holds only when the answer was written from what the tools returned and nothing the model brought along.

## Fit criterion

Every claim in an answer names an entity a tool returned in that conversation; when the rounds the fence allows are spent, the last request can call no tool and is told to write from what the tools returned; and each week's Grounded Answer Rate reads, per chat, the share of questions whose answer had material from the tools.

## Applies to

| Type | Entity |
| --- | --- |
| feature | A visitor asks the model |

## Realization

The model is sent only the host's tools, and the loop makes at most four tool rounds; the last request sets `tool_choice` to none and ends with a note to write from what the tools returned, which a test checks. The system prompt requires every claim to come from a tool answer in the conversation and to name the entity by title, and the answer check marks a claim that names no entity the message's tool answers carry as `unnamed`. Nothing in code forces each claim to name an entity; that rests on the prompt and on the check where a deployment turns it on. The weekly report counts, per language, questions and how many were answered (not refused, and a cited entity or a call that found something); that is a count and not a share, and I did not find the name Grounded Answer Rate in the release, so I could not tell where it is computed.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `test/loop.test.mjs` | satisfies | https://github.com/companygraph/chat-server/blob/v0.38.3/test/loop.test.mjs |
| `lib/prompt.mjs` | satisfies | https://github.com/companygraph/chat-server/blob/v0.38.3/lib/prompt.mjs |
| `lib/report.mjs` | satisfies | https://github.com/companygraph/chat-server/blob/v0.38.3/lib/report.mjs |

## References

| What | URL |
| --- | --- |
| The design of one message answered | https://github.com/companygraph/chat-server/blob/main/docs/design/answering.md |
