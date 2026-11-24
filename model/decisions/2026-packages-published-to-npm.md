---
id: 01a20e3d-f0cd-7b1a-a311-2bdbf8c93597
source: Local
decided: 2026-11-24
kind: Architecture
status: Standing
by: Owner
upholds:
  - Adoption is not taxed
supersedes:
  - A release is its tag, and nothing we make is published to a registry
---

# A package another company builds on is published to npm from its tag

> A release is still its tag, and the meta-model, the MCP server and the chat server are published from that tag to npm under the `@companygraph` scope by the release itself, through trusted publishing and with no token, so a company whose package manager refuses dependencies from git takes them by version.

## The question

Whether the three packages other companies build on stay reachable only by a tag in git. It had to be decided in November 2026, when the first company building on them moved its desktop app to a package manager that refuses dependencies from git for supply-chain reasons, those a dependency brings in included, so a tag stopped being something it could take.

## Alternatives

| Option | Why not |
| --- | --- |
| Publish nothing; a consumer vendors the packages or keeps a fork | Every consumer whose tooling refuses git carries our code in its own repository and takes each release by hand. |
| The consumer publishes the packages under its own name | Our packages reach other companies under a name we do not hold, from a release we did not make, and can differ from the tag. |
| Publish with a token held in CI | One more secret to keep, and the way a stolen token publishes a version nobody reviewed. |
| Publish to GitHub Packages | A consumer has to authenticate to install even a public package there, and point its package manager at a second registry for one scope. |
| Publish everything we make, the design system and the Obsidian plugin too | Nobody takes those through a package manager, and an entry no consumer needs is one more thing to keep in step. |

## Why

The call it replaces turned on three costs: a publish token held in CI, a package that could differ from what was reviewed, and two ways to take one release. Trusted publishing removes the token: npm accepts a version only from the workflow GitHub vouches for, run at the tag. None of the three packages has a build step, so what is published is the files at the tag, and the provenance npm records names the commit they came from. The two ways remain, and they cannot disagree, because a version on npm is made only by the tag of the same version. That call held "for as long as a tag carries everything a consumer takes from a release", and for a consumer whose package manager refuses git it no longer does.

## Consequences

A release of the three packages is still a tag with its notes, and publishing it is a job the tag runs, not a step anyone takes; tags are the owner's alone, so only the owner starts one. The owner holds the `companygraph` organization on npm, and all three packages refuse tokens. A consumer takes a release by tag or by version and gets the same files either way. The packages take each other from npm, because a dependency from git inside a package brings back what the consumer's package manager refuses. Everything else we make stays a tag and nothing more. For the call to stay right, a package must stay without a build step, or build in the publishing job from the tag alone, and no version may reach npm except from its tag.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| concept | Release | | changed it |

## References

| What | URL |
| --- | --- |
| The rule in the shared conventions | https://github.com/robertblust/conventions/blob/main/conventions/WORKING.md |
| npm's trusted publishing | https://docs.npmjs.com/trusted-publishers |
