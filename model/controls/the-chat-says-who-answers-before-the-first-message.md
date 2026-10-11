---
id: 01a129b3-87e1-7cc9-8321-32b1ca586d28
source: Local
kind: preventive
mode: automated
mitigates:
  - A visitor takes an answer for a person's
enforces:
  - A visitor is told an agent answers
---

# The chat says who answers before the first message

> The chat widget opens on a notice that says, first and in its own words, that an AI answers and not a person, then where the message goes and that it goes to the model and to Claude through Anthropic's API, before anything is sent.

## How it is carried out

The widget our sites embed, on every page it is deployed on and in the page's language: when the chat opens, it shows the notice at the top of its log, under a rail in the terminal's amber, opening with the sentence that an AI answers here and not a person, in the panel's ink, then naming the host the message goes to, that the host asks the model and Claude through Anthropic's API, and that nothing is sent until the visitor presses send. A question handed to the chat by a page, from a chip or a link, is not sent on arrival either; it waits under the notice until the visitor sends it. The words are the widget's own and change only with a release of the design that every site then takes.

## Applies to

| Type | Entity | Owner |
| --- | --- | --- |
| process | Answering | |

## References

| What | URL |
| --- | --- |
| The widget, with the notice in English and German | https://github.com/robertblust/design/blob/main/assets/chat.js |
| The surface the notice appears on | https://companygraph.io/model/#01a0c9f6-5458-7276-aae9-86088e4eb1e0 |
