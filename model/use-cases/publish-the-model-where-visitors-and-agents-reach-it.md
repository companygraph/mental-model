---
id: 01a1312c-3dd6-7d38-a18b-e74865f3e0e6
source: Local
level: user goal
scope: system
primary-actor: Owner
features:
  - An agent reads the model
  - A visitor asks the model
realization: Main scenario released
---

# Publish the model where visitors and agents reach it

> The owner has the model served to agents over MCP and to visitors through a chat beside it, from the company's own cloud project, at one commit the owner pinned, with nothing the company wrote passing through anyone else.

## Stakeholders and interests

| Stakeholder | Interest |
| --- | --- |
| Owner | The pin theirs to move, and a deployment that serves nothing from a commit that does not resolve |
| Visitor | An answer at the commit the host pins, and the page each claim came from |
| Answerer | A host whose tools answer at one commit, and a fence it can write inside |

## Preconditions

- The model is a repository the company keeps where it keeps its code.

## Trigger

The owner decides to publish the model, or moves the pin to a later commit.

## Main success scenario

| Step | Actor | Action |
| --- | --- | --- |
| 1 | Owner | Names, in the deployment, the instance and the commit it serves |
| 2 | System | Draws the graph once at that commit when the image is built, resolving every edge before the first question |
| 3 | System | Serves the graph over MCP, every answer naming the commit, and the chat beside it answers from those tools |
| 4 | Owner | Records each place the model is published as a surface in the model |

## Extensions

| Step | Condition | Handling |
| --- | --- | --- |
| 2a | A page at that commit names nothing | No graph is drawn and nothing is served from that commit |
| 3a | The host moves to a new commit while a chat runs | The next message reads the model's types and questions again, and the message answered names the new commit |

## Minimal guarantees

- Nothing is served from a commit whose model does not resolve.
- Nothing the company writes passes through us; what leaves is what a chat visitor sends, to the language model the deployment names.

## Success guarantees

- Every answer from the server and from the chat names the pinned commit.

## Realization

The deployment's `source.json` names the instance and the commit it serves, and `deployment.json` and `chat/chat.json` name its project and hosts (step 1). The workflow it calls from mcp-server v0.69.0 draws the graph once from that commit with the parser, which fails an unresolved name, before it builds the image (2, 2a), and serves it over MCP with every answer naming the commit while the chat beside it answers from those tools (3); chat-server reads the host's types and questions again when the commit moves and names the new commit in `done` (3a, tested in `host.test.mjs`). The deployment's tests, run before the image is built, check that the snapshot is the pinned commit and that every tool answers inside its schema with the commit. Step 4 is the owner's edit to the model. Missing for the next level: no test walks a question through the chat, and none feeds the build a page that names nothing.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `source.json` | satisfies | https://github.com/companygraph/mcp-companygraph-io/blob/868854216c611db2ff536820d04f45b463b19c08/source.json |
| `.github/workflows/deploy-google.yml` | satisfies | https://github.com/companygraph/mcp-server/blob/v0.69.0/.github/workflows/deploy-google.yml |
| `deploy/test/tools.mjs` | satisfies | https://github.com/companygraph/mcp-server/blob/v0.69.0/deploy/test/tools.mjs |
| `test/host.test.mjs` | satisfies | https://github.com/companygraph/chat-server/blob/v0.38.3/test/host.test.mjs |

## References

| What | URL |
| --- | --- |
| The server | https://github.com/companygraph/mcp-server |
| The chat | https://github.com/companygraph/chat-server |
| The deployment that serves this model | https://github.com/companygraph/mcp-companygraph-io |
