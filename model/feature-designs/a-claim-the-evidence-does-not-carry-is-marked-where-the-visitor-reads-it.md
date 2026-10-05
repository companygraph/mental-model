---
id: 01a10a8f-54f9-72ca-bd55-1774d0d676e9
source: Local
refines: A chat answer marks the claims its evidence does not carry
contexts:
  - Answering
decisions:
  - A model that writes no text checks every claim of the chat's answers
---

# A claim the evidence does not carry is marked where the visitor reads it

> After the last sentence of an answer, the chat reads each claim back against the tool answers that carried the entities it names and sends every verdict before the answer ends, so the page marks what the evidence does not carry and the kept line counts it.

## Operational principle

A visitor asks the chat in English what a skill rests on; the answer streams, and after its last sentence the chat reads each claim back against the tool answers that carried the entities it names and sends every claim's verdict and probability before the answer ends; the page underlines the one sentence the evidence carries only in part, a line under the answer says one claim was marked, and the kept line counts the answer's claims and the one not carried.

## Scenarios

### SC-V1: A carried claim is left as it is

Given an English answer whose sentence names a skill and says what the skill's tool answer says, when the answer is checked, then the claim's verdict is `supported` and nothing in it is marked.

### SC-V2: A claim carried in part is marked

Given an English answer whose sentence says what its entity's tool answer says and one thing more, when its `partial` verdict comes with a probability above the deployment's threshold, then the page underlines the sentence as carried in part, a note on hover or focus says so, and a line under the answer says one claim was marked.

### SC-V3: A title no tool returned

Given a sentence that writes the title of an entity of the model that no tool returned in this message, when the answer is checked, then the claim is `unsourced`, carries no probability and is not marked, and the kept line counts it as not carried.

### SC-V4: A claim about the schema keeps its verdict

Given a sentence that names no entity and says what a tool's answer about a type says, when the answer is checked, then the claim keeps the judge's verdict rather than counting as `unnamed`.

### SC-V5: Nothing is said where a tool answered

Given an answer that says the model holds nothing on the matter in a message where a tool call returned rows, when the answer is checked, then the claim is `withheld` and counts as not carried.

### SC-V6: A German answer is checked and not marked

Given an answer written in German, on either language's page, when the answer is checked, then its verdicts are sent with no threshold, nothing in it is marked, and the kept line counts its claims.

### SC-V7: The check cannot run

Given a judge that does not answer within the check's budget, when the answer ends, then no verdict is sent, the answer ends as it would have, and the kept line carries no count of claims.

## Uses

| Type | Entity | Context |
| --- | --- | --- |
| concept-design | Message | Answering |
| concept-design | Claim | Answering |
| concept-design | Kept question | Answering |
| domain-event | Answer checked | Answering |
| domain-event | Message answered | Answering |
| domain-event | Question kept | Answering |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/chat-server/blob/main/lib/verdict.mjs |
| Implementation | https://github.com/companygraph/chat-server/blob/main/lib/loop.mjs |
| Implementation | https://github.com/robertblust/design/blob/main/assets/chat.js |
| The design, with what was measured | https://github.com/companygraph/chat-server/blob/main/docs/superpowers/specs/2026-09-26-the-answer-is-checked-design.md |
