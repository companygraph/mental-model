---
id: 01a1312d-161d-7b5f-a34e-0cae94d0d90c
source: Local
kind: functional
modality: must
realization: Verified
---

# A claim the evidence does not carry is marked before the answer ends

> After an answer's last sentence, each claim is read back against the tool answers that carried the entities it names, and every verdict reaches the page before the answer ends.

## Why

An answer can name the right entity and say something about it the entity does not bear out, and the visitor deciding which sentences to trust needs that shown where they read, not in a report later. A verdict that arrived after the answer closed would mark nothing.

## Fit criterion

Given a claim whose verdict is carried in part, with a probability above the deployment's threshold, the page underlines the sentence, a note on hover or focus says so, a line under the answer says one claim was marked, and the kept line counts it; given a judge that does not answer within the check's budget, the answer ends as it would have and the kept line carries no count.

## Applies to

| Type | Entity |
| --- | --- |
| feature | A chat answer marks the claims its evidence does not carry |

## Realization

Where a deployment checks its answers (`verdict: true` with a threshold of 0.8 in the deployment's `chat/chat.json`), the chat-server reads each claim back against the tool answers, sends one `verdict` event after the last `text` and before `done`, and writes the counts to the kept line; a judge that fails or overruns its budget leaves no `verdict` and no count, and tests check the order, the budget case and the counts. The site's `chat.js` marks a claim carried in part or contradicted above the threshold with an underline, shows a note on hover or focus, and writes a line under the answer, "2 statements here aren't fully backed by the model's pages." in the test's case; the design package's tests check the marks, the threshold, the note on hover and on focus, the German page, an answer that ended in an error and a stream that ends without `done`. The deployed chat is `chat-server` v0.38.3 with the widget of design v0.158.x.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `test/verdict.test.mjs` | verifies | https://github.com/companygraph/chat-server/blob/v0.38.3/test/verdict.test.mjs |
| `test/chat-claims.test.mjs` | verifies | https://github.com/robertblust/design/blob/v0.158.2/test/chat-claims.test.mjs |
| `chat.js` | satisfies | https://github.com/companygraph/companygraph.github.io/blob/3f8e4a25f599cc0e3c77cce8cce17e585d7a6b0e/chat.js |
| `chat/chat.json` | satisfies | https://github.com/companygraph/mcp-companygraph-io/blob/868854216c611db2ff536820d04f45b463b19c08/chat/chat.json |

## References

| What | URL |
| --- | --- |
| The design, with what was measured | https://github.com/companygraph/chat-server/blob/main/docs/superpowers/specs/2026-09-26-the-answer-is-checked-design.md |
