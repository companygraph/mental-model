---
id: 01a1312c-f784-7d5d-b36c-d380130e0b09
source: Local
kind: functional
modality: must
follows:
  - A visitor is told an agent answers
realization: Released
---

# A visitor is told before the first message that an agent answers

> The chat tells the visitor, before the first message is sent and in the language of the page, that an agent writes the answer from the model and which company's language model it goes through.

## Why

A fluent answer in the company's own voice is not obviously an AI's, and whoever provides a system that interacts with people is obliged to tell them so no later than the first interaction. The company's rule carries that obligation, and the chat is where it is kept.

## Fit criterion

On every page the chat is deployed for, in each of its languages, the notice is shown before the visitor can send a message, and it names the language model's company.

## Applies to

| Type | Entity |
| --- | --- |
| feature | A visitor asks the model |

## Realization

The site's `chat.js`, which every page with the chat loads, opens the panel on an intro whose notice reads "An AI answers here, not a person." followed by a sentence saying the message goes to the host, which asks the model and Claude through Anthropic's API, with a link to the privacy page; the German page reads "Hier antwortet eine KI, keine Person." and the same sentence through Anthropics API. The notice is written into the intro by `writeNotice`, and the intro stands before the prompt line and the send control. A test in the design package checks that the notice comes first in the intro, before the question rows and the prompt line, and that its text says nothing is sent until the visitor presses send. No test checks that the notice names Anthropic, that the German text is shown, or that the notice is present on each page the chat is deployed for. The chat-server release ships no widget, so the notice rests on the site's file.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `chat.js` | satisfies | https://github.com/companygraph/companygraph.github.io/blob/3f8e4a25f599cc0e3c77cce8cce17e585d7a6b0e/chat.js |
| `test/chat-ask.test.mjs` | satisfies | https://github.com/robertblust/design/blob/v0.158.2/test/chat-ask.test.mjs |
| `test/chat-terminal.test.mjs` | satisfies | https://github.com/robertblust/design/blob/v0.158.2/test/chat-terminal.test.mjs |

## References

| What | URL |
| --- | --- |
| Article 50 of the Regulation, the transparency obligations | https://artificialintelligenceact.eu/article/50/ |
