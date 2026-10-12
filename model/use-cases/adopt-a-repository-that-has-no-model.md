---
id: 01a1312c-2ed8-7ae4-b836-921feb644472
source: Local
level: user goal
scope: system
primary-actor: Owner
features:
  - A repository is held to one form and told which pins are behind
---

# Adopt a repository that has no model

> The owner has a repository with no model, a site, a service or a server, held to the one Markdown form and told which of the releases and commits it takes have moved on, without anything moving them.

## Stakeholders and interests

| Stakeholder | Interest |
| --- | --- |
| Owner | A pin that is behind read as intent until they say it is drift |
| Writer | One form for the Markdown, whichever tool wrote it last |

## Preconditions

- The folder holds no manifest.

## Trigger

A repository around the model is to run under the same machinery an instance runs.

## Main success scenario

| Step | Actor | Action |
| --- | --- | --- |
| 1 | Owner | Runs the adopt command on the folder |
| 2 | System | Writes a manifest with a tooling and no core, the workflow, the seat hook and a pins file |
| 3 | Owner | Declares each pin in the pins file: the file that holds it and the repository it takes |
| 4 | Writer | Pushes a change, and the workflow holds every Markdown file to the one form |
| 5 | System | Reports each declared pin's reading against its upstream's newest tag, writes nothing, and exits 0 |

## Extensions

| Step | Condition | Handling |
| --- | --- | --- |
| 4a | The repository's own lint configuration turns off a rule of the form | A file breaking that rule still fails |
| 5a | A pin is behind | Its reading is behind and names the newest tag, and the pin is left where it is |
| 5b | A package file takes a repository by tag that the pins file does not declare | That pin's reading is unmanaged, and its upstream is not asked |
| 5c | A declared pin's file holds no line for its repository | Its reading is missing, and the report exits 1 |

## Minimal guarantees

- No pin is moved by the machinery; a pin behind is read and left.

## Success guarantees

- The repository runs the form alone under the same workflow an instance runs, and its pins are read against their upstreams.

## References

| What | URL |
| --- | --- |
| The machinery outside the family | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-10-01-the-machinery-outside-the-family-design.md |
| The workflow a repository calls | https://github.com/companygraph/meta-model/blob/main/.github/workflows/repository-check.yml |
