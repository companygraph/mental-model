---
id: 01a10042-634e-7873-b1b0-3cf8b63cb19a
source: Local
refines: A visitor asks the model
contexts:
  - Answering
  - Serving
decisions:
  - The server only reads, and answers at one named commit
  - A model is written in one language
---

# An answer rests on the entities the tools returned

> A visitor's message is answered by a model that may only ask the host's tools, and every entity the answer read is handed to the page to link, so each claim can be checked where it is mastered.

## Operational principle

A visitor asks a site's chat in their own words what one skill rests on; the model searches the host, gets the skill, and writes the answer from what came back, while the skill streams out as a cite and every entity its answer listed as a name, so the visitor opens the skill's page from under the answer and checks the claim against the commit the answer names.

## Scenarios

### SC-A1: An entity fetched twice is cited once

Given a message whose rounds fetch the same entity twice, when the answer streams, then that entity is cited once, with its title, its type and the address of its page.

### SC-A2: A list's entities are named

Given a tool that answers with a list of skills, when the answer is streamed, then each skill in the list is given to the page once as a name with its id, so the page links its title where the answer writes it, and a skill the message cites is not named again.

### SC-A3: The last round calls nothing

Given a model still asking for tools when the rounds the fence allows are spent, when the last request is made, then it can call no tool and is told to write the answer from what the tools returned, and to say the model does not say where they did not.

### SC-A4: A learner's English is answered in English

Given a message on the German page, written in English words with German word order, when it is put to the model, then the model is told to answer in the language the message's words are in, and the page's language only where they do not tell.

### SC-A5: A German answer names in German first

Given a German question answered after a tool round, when the model writes, then it has just read the naming note, which asks for each entity's name in Swiss Standard German first and its exact title in parentheses after, as **Kundenliste** (The customer list).

### SC-A6: The day's share is spent

Given a meter whose day's share is spent, when a visitor sends a message, then it is refused before the model is asked, the refusal names the next midnight UTC as the moment it lifts, and the question is kept with the refusal's code.

### SC-A7: The visitor leaves mid-answer

Given a visitor who closes the page while the model is still asking tools, when the next round would begin, then no further request is made, the meter is settled to what was spent, nothing more is sent, and the question is kept with what the answer had gathered.

### SC-A8: The host is re-pinned under the chat

Given a host re-pinned to a new commit while the chat runs, when a tool's answer names that commit, then the next message reads the model's types and questions again, and the message answered names the new commit.

## Uses

| Type | Entity | Context |
| --- | --- | --- |
| concept-design | Message | Answering |
| concept-design | Cite | Answering |
| concept-design | Name | Answering |
| concept-design | Fence | Answering |
| concept-design | Meter | Answering |
| concept-design | Kept question | Answering |
| domain-event | Entity cited | Answering |
| domain-event | Message answered | Answering |
| domain-event | Question kept | Answering |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/chat-server/blob/main/lib/loop.mjs |
| The interface | https://github.com/companygraph/chat-server/blob/main/docs/INTERFACE.md |
