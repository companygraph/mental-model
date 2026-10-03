---
id: 01a10042-5ea4-7ef8-af18-8e8675267d6e
source: Local
classification: supporting
realizes:
  - Core
decisions:
  - The server only reads, and answers at one named commit
  - A model is written in one language
---

# Answering

> Puts a visitor's message to a model that may only ask the MCP host's tools, and streams back an answer that cites the entities it read, within a fence of length, rounds and spend. What the model says, and at which commit, is left to Serving.

## Responsibilities

- Refuse a message before the model is asked when it is not a conversation that ends with the visitor, when a turn is too long, when its page is not one the deployment named, or when its address has spent its hour
- Give the model the host's instructions and tools as the host gave them, with the map of the model's types and the questions it answers, read again when the host names another commit
- Let the model ask the tools for a bounded number of rounds, and make the last request one that can call nothing
- Cite each entity a tool answered with whole, once a message, and name every entity a list answer held, so the page can link it where the answer writes it
- Hand a diagram the host drew to the page to draw, and let the model read only what it shows
- Tell the model to answer in the language the visitor's last message is written in, and in any other language than English to name each entity in that language before its exact title
- Count what every request to the model costs against the day's share and the month's ceiling, before the request and after it
- Keep one line of every question asked, with no address and no word of the answer
- Stop where the visitor left, and spend nothing more

## Relationships

| Context | Pattern |
| --- | --- |
| Serving | conformist |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/chat-server/blob/main/lib/loop.mjs |
| The interface | https://github.com/companygraph/chat-server/blob/main/docs/INTERFACE.md |
| The design | https://github.com/companygraph/chat-server/blob/main/docs/superpowers/specs/2026-09-22-chat-server-design.md |
