---
id: 01a10042-5b26-7cfd-b2c8-f1c072acfe16
source: Local
classification: supporting
realizes:
  - Core
decisions:
  - The server only reads, and answers at one named commit
---

# Serving

> Answers an agent's questions about one instance from a snapshot taken at one commit, a page at a time, and refuses what it cannot answer with a code a program can branch on. What the names on a page mean is left to Resolution, whose graph it serves untouched.

## Responsibilities

- Take a snapshot of an instance at the commit a deployment pins, and serve nothing else for as long as it runs
- Name the commit, the repository, the core release and the parser release on every answer and every refusal
- Answer the vocabulary's own questions: which types exist, what one entity says, which edges join it, what evidence a claim rests on
- Find entities by a substring, an exact canonical name or the stems of a visitor's words
- Hand a long list out a page at a time, in one fixed order, and refuse a cursor written for another commit
- Refuse an ambiguous name with every candidate named, never answering with the first match
- Write nothing back to the model

## Relationships

| Context | Pattern |
| --- | --- |
| Resolution | conformist |

## Consumes

| Type | Entity | Context | Reaction |
| --- | --- | --- | --- |
| domain-event | Graph drawn | Resolution | Take a snapshot of the graph as drawn, with the commit and core release it was read at |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/mcp-server/blob/main/lib/model.mjs |
| The interface | https://github.com/companygraph/mcp-server/blob/main/docs/INTERFACE.md |
