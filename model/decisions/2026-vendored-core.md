---
source: Local
decided: 2026-08-25
kind: Architecture
status: Standing
by: Owner
upholds:
  - Run on what we publish
---

# Core is vendored into an instance at a release its manifest names

> An instance carries a copy of core at the release its manifest names, with a hash per file, and moves to a later release only when it decides to.

## The question

How the vocabulary reaches a company's model, and who decides when a change to it reaches theirs. It had to be decided when the tooling was designed, in August 2026, because `init`, `upgrade` and `check` all depend on the answer and the first instance was about to be written.

## Alternatives

| Option | Why not |
| --- | --- |
| Resolve core at read time, from the newest release | A change to the vocabulary would move under every model at once, and nobody could say which rules a page was written against. |
| A git submodule pointing at core | It pins a commit and not a release, carries no hash per file to tell drift from an edit, and asks every adopter to know submodules. |

## Why

The version number below 1.0 is doing work: the vocabulary is free to change, and an instance decides when to take a change because core is vendored at a release its manifest names rather than resolved at read time. A release can then say what an instance must do about it, and most say nothing, which is what lets the vocabulary keep moving without moving anyone's model underneath them.

## Consequences

`upgrade` owns the vendored files and nothing else; a checker that is not the release the manifest names refuses to run; a file edited inside `meta/` shows as drift. What it gave up is a single current vocabulary: every instance may be at a release of its own, and every consumer names the one it reads. It stays right for as long as a release says what an instance must do about it.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| concept | Core | | changed it |
| concept | Pin | | made it |
| concept | Instance | | changed it |

## References

| What | URL |
| --- | --- |
| The tooling specification | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-08-25-companygraph-tooling-design.md |
