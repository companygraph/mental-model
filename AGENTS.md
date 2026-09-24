<!-- conventions · v1.29.0 -->
Shared conventions of the robertblust, guestgraph and companygraph organizations live in `conventions/`, vendored from robertblust/conventions at the release `conventions.json` names. Read them before writing or committing anything here.

- `conventions/WRITING.md` — how we write: one voice, three registers, English and German.
- `conventions/WORKING.md` — how we work with git and GitHub.
- `conventions/REPOSITORIES.md` — the family: what each repository is and what pins what.
- `conventions/WRITER.md`, `conventions/TRANSLATOR.md`, `conventions/EDITOR.md`,
  `conventions/BACKREADER.md`, `conventions/GLOSSARY.md`, `conventions/GERMAN.md` — the four roles
  that make a text, the terms they keep and the German they write.

Everything below this block is this repository's own. `sh conventions/conventions-sync check` says whether the copy matches the release, `sync` brings it to the release the pin names, and `sh conventions/conventions-check` holds this repository's own Markdown to `WRITING.md`, and `sh conventions/conventions-format` to its one form, which `fix` writes. Edit a shared file in robertblust/conventions, never here.
<!-- end conventions -->

# CompanyGraph — working conventions

This repository is a CompanyGraph instance. The rules it is held to are vendored under `meta/core/`, and `meta/core/CONVENTIONS.md` is the one to read before writing anything here: one file per entity, a reference written as a canonical name, and a schema for every type under the same folder.

The mechanical half of those rules is checked by CI, and locally by `npx --yes github:companygraph/meta-model#v<tooling> check`, where `<tooling>` is the release `.companygraph/manifest.json` names; the package is not on npm, so a bare package name finds nothing. What no check reads is each schema's `## Writing rules`, which an agent judges by reading them against the entity.

Everything below this line is this instance's own: how it is written, what it does not claim, and where its facts are mastered.

## What this is

CompanyGraph, described in the vocabulary CompanyGraph publishes. What `model/` holds is the project behind the meta-model: where it is going, what it will and will not do, how it does its one kind of work, and the places the model is published. `meta/core/` is core, vendored and never edited here; `.companygraph/manifest.json` records which release and a hash per file.

## How it is written

Prose follows `conventions/WRITING.md`, and an entity answers to its schema's `## Writing rules` in `meta/core/` as well. No check reads those; an agent judges them by reading them against the entity it is writing.

Entries are written and reviewed one at a time — what it says, the case against it, a proposal, and the owner decides — because these are editorial facts about a company rather than a schema being filled in. Nothing is committed ahead of that review.

## What it does not claim

**No person is described here.** No `skill`, `experience` or `proficiency-level` is written in this repository, and the one profile it carries is an agent, by decision and not for the moment. CompanyGraph is operated by the company of one that `robertblust/mental-model` describes, and that is where the person is described; a profile for a person here would put one canonical name in two instances with two sets of facts behind it, and the second set would go stale without a sound. A `role` is a seat and the schema forbids it to name its holder, so `model/roles/` carries the seats the processes name and says nothing about who sits in them. What a seat is held by is said once, by the agent profile listing the seats an agent holds: a seat no profile names is held by a person, and which person is a fact this repository does not carry.

## Where its facts are mastered

Every page is mastered here — `source: Local`, corrected in this repository and nowhere else. There is no upstream to correct first.

A fact enters from prose that is already published and already reviewed: the organization profile on GitHub, the pages of companygraph.io, the meta-model's README and the specs beside it, and the introduction talk. A claim that cannot be traced to one of those does not go in, however true it sounds; the guard is against invention by whoever is editing.

## Checks

Two jobs, both required by the ruleset on `main`: `companygraph`, which calls meta-model's `instance-check.yml` at the release its workflow names and is shown by GitHub as `companygraph / companygraph`, and `conventions`, called from robertblust/conventions at the tag `conventions.json` names and shown as `conventions / conventions`. A ruleset requires a job by its id, so neither is renamed without its ruleset.

`meta/` is excluded from the prose check and from the Markdown form because it is core, vendored and never edited here; its words are core's to hold, and holding them here would fail this repository for a change made somewhere else.
