---
id: 01a10042-63b0-7246-9f9b-acb04d896c46
source: Local
refines: A repository is held to one form and told which pins are behind
contexts:
  - Vendoring
  - Checking
decisions:
  - A release is its tag, and nothing we make is published to a registry
---

# A repository takes the form and reads its pins without moving them

> A repository with no model is adopted into the same machinery an instance runs, its Markdown held to the one form and its pins read against their upstreams without one being moved.

## Operational principle

A site's repository is adopted: it gets a manifest naming the release and no core, a workflow that runs the form at that release, the seat hook and a `pins.json` declaring its tooling pin; its pull requests are then held to the form, and once a newer release is tagged the pin report reads that pin as behind, names the newer tag and moves nothing.

## Scenarios

### SC-H1: A repository without a model is adopted

Given a folder with no manifest, when it is adopted, then it holds a manifest with a tooling and no core, the workflow, the seat hook and a `pins.json`, and checking it runs the form alone.

### SC-H2: A repository's own configuration does not change the form

Given a repository whose own `.markdownlint` configuration turns off a rule of the form, when it is checked, then a file breaking that rule still fails.

### SC-H3: A pin behind is read and left

Given a `pins.json` whose tooling pin names a tag older than the upstream's newest, when the pins are reported, then the pin's reading is behind and names the newest tag, nothing is written and the report exits 0.

### SC-H4: A pin nobody declared

Given a `package.json` that takes a repository by tag and a `pins.json` that does not declare it, when the pins are reported, then that pin's reading is unmanaged and its upstream is not asked.

### SC-H5: A declared pin with no line

Given a `pins.json` entry whose file holds no line for its repository, when the pins are reported, then its reading is missing and the report exits 1.

## Uses

| Type | Entity | Context |
| --- | --- | --- |
| concept-design | Manifest | Vendoring |
| concept-design | Pin | Vendoring |
| concept-design | Pin reading | Vendoring |
| domain-event | Repository adopted | Vendoring |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/lib/pins.mjs |
| Implementation | https://github.com/companygraph/meta-model/blob/main/lib/form.mjs |
| Implementation | https://github.com/companygraph/meta-model/blob/main/.github/workflows/repository-check.yml |
| The machinery outside the family | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-10-01-the-machinery-outside-the-family-design.md |
