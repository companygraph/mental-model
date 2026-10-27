---
id: 01a1312b-a50c-7b0c-b291-c4d4056ddb87
source: Local
level: summary
scope: system
primary-actor: Owner
features:
  - A vocabulary to describe a company in
  - An instance is made and kept from one command
includes:
  - Start a company's model
  - Describe the company from its web address
  - Take a pack the company needs
  - Write a page that holds
  - Write a person's profile from their documents
  - Judge the pages against their writing rules
  - Check a change against the schemas
  - Publish the model where visitors and agents reach it
  - Adopt a repository that has no model
  - Move the model to a newer release
realization: Main scenario released
---

# Keep the company's model

> The owner has a model of their company that says what the company knows, passes its checks on every change and is published where people and agents reach it, with nothing in it the owner did not decide.

## Stakeholders and interests

| Stakeholder | Interest |
| --- | --- |
| Owner | A model that holds every fact the company decided to write and nothing else, under rules the company chose |
| Writer | A page whose form and names are held before a push, not after |
| Visitor | An answer about the company that rests on the model and names the page it came from |

## Trigger

A company decides to write down what it knows once, in a structure its people and its agents both read.

## Main success scenario

| Step | Actor | Action |
| --- | --- | --- |
| 1 | Owner | Makes the instance from one command, as Start a company's model says |
| 2 | Owner | Has the agent fill it from what the company already publishes, as Describe the company from its web address says |
| 3 | Owner | Takes the vocabulary a company of its kind needs, as Take a pack the company needs says |
| 4 | Writer | Writes each page the company has a fact for, as Write a page that holds says |
| 5 | Owner | Has a person's profile written from their documents, as Write a person's profile from their documents says |
| 6 | Owner | Asks which pages most likely break a writing rule, as Judge the pages against their writing rules says |
| 7 | Writer | Holds every change to the schemas before it lands, as Check a change against the schemas says |
| 8 | Owner | Serves the model to agents and visitors at one pinned commit, as Publish the model where visitors and agents reach it says |
| 9 | Owner | Holds the repositories around the model, its site and its servers, to the same form, as Adopt a repository that has no model says |
| 10 | Owner | Takes a release the company wants, as Move the model to a newer release says |

## Extensions

| Step | Condition | Handling |
| --- | --- | --- |
| 10a | The release's notes say it adds a rule the instance's pages do not yet keep | The owner writes what the rule asks in the same change as the move, since a page that fails is not merged, and the scenario goes on at 7 |

## Minimal guarantees

- The model stays a repository the company keeps where it keeps its code, and nothing the company writes passes through us.
- No vendored file is overwritten by a move the owner did not force.

## Success guarantees

- The model passes the checks of the release it adopted.
- Every surface shows the model at a commit the owner pinned.

## Realization

Each step is the use case it names, so the page reads as they do. Steps 1 (Start a company's model), 3 (Take a pack) and 10 (Move) are Released end to end in meta-model v0.95.0. Steps 2, 4, 5, 6, 7 and 9 are Main scenario released, and step 8 (Publish) is Main scenario released with the deployment at its deployed commit, so the scenario as a whole sits at that level. Extension 10a is the release notes and the check, both in meta-model. The guarantee that no vendored file is overwritten by a move the owner did not force is tested in meta-model (`upgrade refuses when core was edited inside the instance`). The guarantee that every surface shows the model at a commit the owner pinned rests on the deployment's `source.json` and the site's `source.json`. The page has no test of its own and none could walk ten use cases.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `bin/companygraph.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/bin/companygraph.mjs |
| `verify/cli.test.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/cli.test.mjs |
| `source.json` | satisfies | https://github.com/companygraph/mcp-companygraph-io/blob/868854216c611db2ff536820d04f45b463b19c08/source.json |

## References

| What | URL |
| --- | --- |
| The meta-model, with what an instance is and how it is made | https://github.com/companygraph/meta-model |
| The site's page on the command | https://companygraph.io/cli/ |
