---
id: 01a1312d-4501-7e47-abc4-8b179c53d140
source: Local
kind: functional
modality: must
realization: Released
---

# A question is answered in the language of its words

> An answer is written in the language the message's words are in, and in the page's language only where the words do not tell.

## Why

A visitor is owed an answer in their words, and the page they are on is a weaker signal of their language than what they typed: a learner writing English on the German page wants English back. A German answer names each entity in Swiss Standard German first, with its exact title after, so the reader can both read the name and find the page.

## Fit criterion

A message in English words with German word order, sent from the German page, is answered in English; and a German answer written after a tool round names each entity in Swiss Standard German first with its exact title in parentheses after.

## Applies to

| Type | Entity |
| --- | --- |
| use-case | Ask the company a question |

## Realization

After every tool round the loop appends a note that quotes the visitor's last message and says to write in the language its words are in, even where their grammar is a learner's; the system prompt says the same, and a test holds both. The naming rule says an answer in another language names each entity in that language first with the exact title in parentheses, with Swiss Standard German in the example. The `done` event reports the language the answer is written in, read from its words. The English message with German word order from the German page is the case the note was written for; the release reports it measured by hand in comments, and no test can observe what the model writes, so the behavior is shown to be asked for and not to be obtained.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `test/prompt.test.mjs` | satisfies | https://github.com/companygraph/chat-server/blob/v0.38.3/test/prompt.test.mjs |
| `lib/prompt.mjs` | satisfies | https://github.com/companygraph/chat-server/blob/v0.38.3/lib/prompt.mjs |

## References

| What | URL |
| --- | --- |
| The design of the prompt | https://github.com/companygraph/chat-server/blob/main/docs/design/prompt.md |
