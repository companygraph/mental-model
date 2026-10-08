---
id: 01a10042-5719-7ad4-b25d-d53630b4884b
source: Local
classification: core
realizes:
  - Core
decisions:
  - Agents write the model, and a person approves every change to it
  - Claude is the first agent an instance supports, and not the only one
  - The schema written as prose is the only schema
---

# Procedures

> The procedures an agent follows where the work is a judgment and not a rule: building an instance from a company's web address, writing a profile from a person's documents, recording a source's terms and consent, judging pages against their writing rules, producing a surface and exporting the model. Whether a page has the shape its schema asks for is left to Checking.

## Responsibilities

- Build an instance from what a company publishes, keeping only what a schema has a place for and what the operator keeps
- Write a profile, or extend one, from a folder of a person's documents, reusing the skills, levels, kinds and seats the model already holds
- Record on a source the terms its content is published under and each consent its use needs, as the operator states them
- Judge every page against its schema's writing rules after the mechanical checks, and say what was not checked
- Produce a surface's content from the model by the rules its page records, and stop where a rule needs what the model does not hold
- Package the model for an agent and for a notebook from one walk, so that both carry the same entities
- Propose every level, seat and sentence in someone's own voice, leave each decision to the operator, and leave the commit to them

## Relationships

| Context | Pattern |
| --- | --- |
| Checking | conformist |
| Vendoring | conformist |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills |
| Where init installs them | https://github.com/companygraph/meta-model/blob/main/lib/plan.mjs |
