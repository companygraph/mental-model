---
id: 01a1312c-9a9a-739b-917c-93031643590f
source: Local
kind: functional
modality: must
realization: Verified
---

# An answer names the commit it was read at

> Every answer a surface gives from the model, a tool's, a chat's or a page's, names the commit of the model it was read at.

## Why

An answer can be checked against the same bytes later only when it says which bytes, and two answers given a week apart can be told apart only by the commit each names. Without it, a surface answers about a model's current state in general, which no one can hold it to.

## Fit criterion

Every tool answer of the server carries the commit under `model`; every chat answer names the commit each entity it cites was read at; and the model page draws the commit it was built at beside the figure.

## Applies to

| Type | Entity |
| --- | --- |
| feature | An agent reads the model |
| feature | A visitor asks the model |
| feature | The vocabulary on the web |

## Realization

Every tool answer and refusal of the server carries `model.commit`, its output schemas require `model`, and a test calls each tool and checks it; the entity addresses it returns are built at that commit and a test checks them. The deployment's own tests repeat that over its snapshot before the image is built. A chat `cite` event carries the address the host's tool returned, `blob/<sha>/`, and the widget draws each cite's mark as "<title> on GitHub, commit <sha>" and the answer's commit line from that address, which tests in the design package check; the chat names the commit through each entity's address and not through a field of its own on the event. The model page draws the commit beside the figure from the data's commit, and the site's `verify` suite checks that the drawn commit and the link to the tree are the artifact's.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `test/server.test.mjs` | verifies | https://github.com/companygraph/mcp-server/blob/v0.69.0/test/server.test.mjs |
| `test/chat.test.mjs` | verifies | https://github.com/robertblust/design/blob/v0.158.2/test/chat.test.mjs |
| `verify/model-pages.mjs` | verifies | https://github.com/robertblust/design/blob/v0.158.2/verify/model-pages.mjs |
| `stage.js` | satisfies | https://github.com/companygraph/companygraph.github.io/blob/3f8e4a25f599cc0e3c77cce8cce17e585d7a6b0e/stage.js |

## References

| What | URL |
| --- | --- |
| The server's interface | https://github.com/companygraph/mcp-server/blob/main/docs/INTERFACE.md |
