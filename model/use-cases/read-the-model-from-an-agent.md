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
realization: Released end to end
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

## Realization

mcp-server v0.69.0 has `list_types`, `describe_schema`, `search`, `get_entity`, `find_evidence`, `list_rules` and `describe_rule` (steps 1, 2 and 4), each answering from the snapshot drawn at the pinned commit with references resolved to ids, the `via` that drew each edge and the commit under `model` (3). Lists page with a cursor (5, see Walk a long list a page at a time). An ambiguous name is refused with every candidate's id, and each id then answers (2a, `contract.test.mjs`). A refusal carries a code, details and the sentence, and `describe_errors` serves the codes and the schema of a refusal (2b, `describe-errors.test.mjs`). Every entity is addressed by a stable id apart from the page's address (3a, `stable-ids.test.mjs`). Every tool says it only reads (`server.test.mjs`), so no call changes the model. The tests that read most as the scenario are in `test/contract.test.mjs`, which connects an MCP client over HTTP and checks each tool's answer against its declared schema, including the walks and the refusals; step 6 is the agent's own answer and needs no release.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `test/contract.test.mjs` | verifies | https://github.com/companygraph/mcp-server/blob/v0.69.0/test/contract.test.mjs |
| `test/stable-ids.test.mjs` | satisfies | https://github.com/companygraph/mcp-server/blob/v0.69.0/test/stable-ids.test.mjs |
| `docs/INTERFACE.md` | satisfies | https://github.com/companygraph/mcp-server/blob/v0.69.0/docs/INTERFACE.md |

## References

| What | URL |
| --- | --- |
| The server's interface | https://github.com/companygraph/mcp-server/blob/main/docs/INTERFACE.md |
| The server this model answers at | https://mcp.companygraph.io/ |
