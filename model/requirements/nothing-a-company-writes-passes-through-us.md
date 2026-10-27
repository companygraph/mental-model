---
id: 01a1312c-e88a-7575-8b3a-c7a7cc70c01f
source: Local
kind: constraint
modality: must
realization: Released
---

# Nothing a company writes passes through us

> A company's model, and the server and the chat that serve it, run in the company's own repository and cloud project from the parts we publish, so nothing the company writes passes through us.

## Why

A company that would have to hand over its model to be served has been charged for adoption, and an access layer that costs money is a seat count wearing a different name. What leaves the company's hands is only what a chat visitor sends, which goes to the language model the deployment names.

## Fit criterion

A deployment of the server and the chat names the company's own cloud project and the company's own key or project for the language model, and no request from either reaches a host we run.

## Applies to

| Type | Entity |
| --- | --- |
| product | CompanyGraph Core |

## Realization

A deployment of the server is its own repository calling the release's workflow with its `deployment.json`, which names its Google Cloud project, billing account, region and domain, and the image is built and pushed to that project's registry; the model is read from the company's own repository at the pinned commit. A deployment of the chat names its host and its model host in `chat.json`, and the language model is reached through the company's own Vertex project or through an Anthropic organization's workload-identity federation that `chat.json` names, whose shape the release's `deploy-config.test.mjs` checks; sign-in names the company's own identity issuer. The code of the two servers contains no address of a host the makers run except links in the pages' footers, and the only outbound reads are GitHub's raw files, the language model and the cloud's own log and storage. No test records the requests a running deployment makes.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `deployment.json` | satisfies | https://github.com/companygraph/mcp-companygraph-io/blob/868854216c611db2ff536820d04f45b463b19c08/deployment.json |
| `chat/chat.json` | satisfies | https://github.com/companygraph/mcp-companygraph-io/blob/868854216c611db2ff536820d04f45b463b19c08/chat/chat.json |
| `test/deploy-config.test.mjs` | satisfies | https://github.com/companygraph/chat-server/blob/v0.38.3/test/deploy-config.test.mjs |

## References

| What | URL |
| --- | --- |
| The strategy, where it runs and what leaves | https://github.com/companygraph/mental-model/blob/main/model/strategies/read-only-server-strategy.md |
