---
id: 01a1312c-5cfc-7c71-bd35-b7da880c4254
source: Local
level: user goal
scope: system
primary-actor: Visitor
features:
  - An agent reads the model
includes:
  - Walk a long list a page at a time
---

# Read the model from an agent

> A visitor, through an agent of their own, has the answer the company's model gives at one commit: which types it declares, what one entity says and what evidence a claim rests on, each with the id that stays with the entity.

## Stakeholders and interests

| Stakeholder | Interest |
| --- | --- |
| Visitor | The model's answer at one commit, with nothing added |
| Agent | A code on every refusal and a page for every list, so it never has to guess |
| Owner | No path by which an agent changes the model |

## Preconditions

- The agent's client reaches the server, by its address or from its listing in the public MCP Registry.

## Trigger

The visitor asks their agent something about the company.

## Main success scenario

| Step | Actor | Action |
| --- | --- | --- |
| 1 | Agent | Asks which types the model declares, and what one schema says |
| 2 | Agent | Searches for a named thing, then asks for the entity itself by its id or its address |
| 3 | System | Answers from the graph drawn once at the commit the deployment names: the entity's references resolved to ids, each with the field or column that drew it, and the commit |
| 4 | Agent | Asks what evidence a claim rests on, and which rule governs a page |
| 5 | Agent | Follows a list past its first page, as Walk a long list a page at a time says |
| 6 | Agent | Gives the visitor the answer with the commit it was read at |

## Extensions

| Step | Condition | Handling |
| --- | --- | --- |
| 2a | The name alone is ambiguous, two entities of one type under different owners | The agent asks by id, which no two entities share |
| 2b | A call is refused | The refusal carries a code for a program beside the sentence for a reader, and the agent asks for the codes and the schema of a refusal |
| 3a | The entity's page was renamed since an earlier commit | The edge still joins the same id |

## Minimal guarantees

- The server reports what the model says at one commit and adds nothing.
- No call changes the model.

## Success guarantees

- Every answer the agent passes on names the commit it was read at and the id of each entity it rests on.

## References

| What | URL |
| --- | --- |
| The server's interface | https://github.com/companygraph/mcp-server/blob/main/docs/INTERFACE.md |
| The server this model answers at | https://mcp.companygraph.io/ |
