---
id: 01a1312d-54ac-7c7c-b554-5cb0398ec71d
source: Local
kind: functional
modality: must
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

## References

| What | URL |
| --- | --- |
| The design of one message answered | https://github.com/companygraph/chat-server/blob/main/docs/design/answering.md |
