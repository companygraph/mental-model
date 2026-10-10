---
id: 01a0f0b5-1390-73e6-94f7-d3b510a3dff4
source: Local
decided: 2026-09-04
kind: Architecture
status: Standing
by: Owner
---

# A release is its tag, and nothing we make is published to a registry

> A release of anything we make is a git tag with its notes, and nothing more: nothing is published to npm or any other registry, and whoever takes a release takes it by naming its tag.

## The question

How a release reaches whoever takes it: as a tag in git, or as a package in a registry beside the tag. The first design of the tooling planned a package on npm, run as `npx companygraph@latest`. It had to be decided on September 4, 2026, with the first release of the conventions, because those say how every repository in the family releases and how every other one pins it.

## Alternatives

| Option | Why not |
| --- | --- |
| Publish to npm, with a build at release | A second artifact beside the tag, a publish token to hold in CI, and a package that can differ from what was reviewed. |
| Publish to npm alongside the tag | Two ways to take one release, which a consumer would have to choose between and which could disagree. |
| A separate tooling repository that publishes its own package, as the tooling was first designed | A second release to make and to keep in step with core. |

## Why

One release carries everything: core, the parser, the checks and the command move together under one tag, and every pin in the family, of code or of content, names a tag or a commit. The checker runs from a checkout: an instance's CI checks out the meta-model at the tag its manifest declares and runs the checker from it, so a package in a registry would be a second artifact to keep in step with that checkout. A registry needs an account and a publish token held in CI, one more secret and one more way a release can go wrong. And installing from a tag gets exactly what git holds, where a built package can differ from what was reviewed.

## Consequences

Every consumer takes a release by its tag. The meta-model's command runs straight from one, `npx github:companygraph/meta-model#<tag> <command>`, and the sites, the MCP server and the Obsidian plugin install the package by tag. The package planned for npm was never published, and the command moved into the meta-model, run from a tag, when the command line was designed. What it gave up is taking a release by a bare package name, as a consumer used to a registry would: a bare name finds nothing, and every consumer names a tag. It stays right for as long as a tag carries everything a consumer takes from a release, and what is installed is what was reviewed.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| concept | Release | | changed it |

## References

| What | URL |
| --- | --- |
| The rule in the shared conventions | https://github.com/robertblust/conventions/blob/main/conventions/WORKING.md |
| The command-line specification | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-09-20-the-cli-design.md |
| The first tooling specification | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-08-25-companygraph-tooling-design.md |
