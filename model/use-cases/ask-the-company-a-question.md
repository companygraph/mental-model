---
id: 01a1312c-4d5f-7923-b896-700a5ce8d15f
source: Local
level: user goal
scope: system
primary-actor: Visitor
features:
  - A visitor asks the model
  - A chat answer marks the claims its evidence does not carry
realization: Main scenario released
---

# Ask the company a question

> A visitor asks about the company in their own words and language, and gets an answer that names the entity each claim rests on, says where the model does not say, and sends them to the page the claim came from at the commit it was read.

## Stakeholders and interests

| Stakeholder | Interest |
| --- | --- |
| Visitor | What the model says and nothing else, in their language, with no account and nothing left behind |
| Answerer | A host whose tools answer at one pinned commit, and a fence it can write inside |
| Owner | No claim standing that no tool returned, and nothing spent past the ceiling the deployment wrote down |

## Preconditions

- The page tells the visitor, before the first message, that an agent writes the answer from the model and which company's language model it goes through.
- The host pins a commit of the model, and the deployment names the page the chat is for.

## Trigger

The visitor opens the chat and presses send.

## Main success scenario

| Step | Actor | Action |
| --- | --- | --- |
| 1 | Visitor | Asks, in their own words and language |
| 2 | System | Lets the message through the fence: under the length it allows, from a page the deployment names, inside the hour's, the day's and the month's share |
| 3 | Answerer | Asks the host's tools, up to four rounds: a kind of thing by its type, a named thing by search and then the entity itself |
| 4 | Answerer | Writes the answer from what the tools said, in the language of the message's words, naming the entity each claim rests on, and where the tools said nothing, that the model does not say |
| 5 | System | Streams each entity the answer read to the page once, as a cite or as a name with its id, so the page links it to the model page and to the file at the commit |
| 6 | System | Reads each claim back against the tool answers that carried the entities it names, and sends every verdict before the answer ends |
| 7 | System | Keeps one line: the question, its language, the entities cited, how many tool calls were made and how many found nothing, and whether the fence refused; the answer is not kept |
| 8 | Visitor | Opens the page a claim rests on, at the commit the answer names |

## Extensions

| Step | Condition | Handling |
| --- | --- | --- |
| 1a | The question is not about the model | It is answered with one sentence saying what the chat is for, and no tool is asked |
| 2a | The day's share is spent | The message is refused before the model is asked, the refusal names the next midnight UTC as the moment it lifts, and the question is kept with the refusal's code |
| 3a | The rounds the fence allows are spent while the model still asks for tools | The last request can call no tool, and the model writes the answer from what the tools returned |
| 3b | The host moved to a new commit while the chat runs | The message reads the model's types and questions again, and the answer names the new commit |
| 4a | The message is in English words with German word order, on the German page | It is answered in the language its words are in |
| 4b | The answer is German, after a tool round | Each entity is named in Swiss Standard German first, with its exact title in parentheses after |
| 6a | A claim is carried in part, with a probability above the deployment's threshold | The page underlines the sentence, a note on hover or focus says so, and a line under the answer says one claim was marked |
| 6b | The answer is German | It is checked and not marked, and the kept line counts its claims |
| 6c | The judge does not answer within the check's budget | No verdict is sent, the answer ends as it would have, and the kept line carries no count of claims |
| 7a | The visitor closed the page while the model was still asking tools | No further request is made, the meter is settled to what was spent, and the question is kept with what the answer had gathered |

## Minimal guarantees

- No claim stands that no tool returned in that conversation.
- Nothing more of the question is kept than the question itself and whether the model could answer it, never with an address and never past ninety days, and the answer is not kept.
- Nothing is spent past the ceiling the deployment wrote down.
- Nobody reads the answer before the visitor does.

## Success guarantees

- Every claim names the entity a tool returned it from, and the visitor can open that entity at the commit the answer names.
- Where the tools did not say, the answer says the model does not say.

## Realization

The deployed site's `chat.js` shows the notice before the first message and draws the cites, the underline, the note on hover and the line under the answer (steps 5 and 6a, 8 by the cite's link into the model page and the file at the commit). chat-server v0.38.3 carries the fence of length, page, hour, day and month with the refusal naming the next midnight UTC (2, 2a), the tool loop of at most four rounds with a last request that forbids a tool call (3, 3a), the host's types and questions read again when the commit moves (3b), the language rule and the naming rule (4, 4a, 4b), the `cite` and `names` events (5), the `verdict` event before `done`, German answers unmarked and an unanswered judge leaving no count (6, 6b, 6c), the kept line without address or answer and the settling of the meter when the visitor leaves (7, 7a). Missing: for a question that is not about the model the prompt tells the model to answer through the tools and holds no rule for one sentence on what the chat is for with no tool asked, so extension 1a is not in a release. Tests cover the server steps and the widget separately with the other side's events mocked; none walks a question from the fence to the opened page.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `test/loop.test.mjs` | satisfies | https://github.com/companygraph/chat-server/blob/v0.38.3/test/loop.test.mjs |
| `test/http.test.mjs` | satisfies | https://github.com/companygraph/chat-server/blob/v0.38.3/test/http.test.mjs |
| `test/verdict.test.mjs` | satisfies | https://github.com/companygraph/chat-server/blob/v0.38.3/test/verdict.test.mjs |
| `chat.js` | satisfies | https://github.com/companygraph/companygraph.github.io/blob/3f8e4a25f599cc0e3c77cce8cce17e585d7a6b0e/chat.js |
| `test/chat-claims.test.mjs` | satisfies | https://github.com/robertblust/design/blob/v0.158.2/test/chat-claims.test.mjs |

## References

| What | URL |
| --- | --- |
| The interface, with the kept line's fields | https://github.com/companygraph/chat-server/blob/main/docs/INTERFACE.md |
| The design of one message answered | https://github.com/companygraph/chat-server/blob/main/docs/design/answering.md |
| The chat this model answers at | https://chat.companygraph.io/ |
