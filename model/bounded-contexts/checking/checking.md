---
id: 01a10042-5ce7-7756-9ce4-1cf2a4435aa2
source: Local
classification: core
realizes:
  - Core
decisions:
  - The schema written as prose is the only schema
  - Core is vendored into an instance at a release its manifest names
  - A section is open and a field is closed
  - A reference resolves by its declared type, never by name alone
  - Every entity carries an id that outlives its name
---

# Checking

> Holds an instance's pages to the schemas and rules of the core it vendored, as the release of the checker its manifest names, and reports every finding before a change lands. Whether a page keeps its schema's writing rules is left to the agent pass of Procedures.

## Responsibilities

- Read the schemas only from the core and packs the instance vendored, never from the checker's own copy
- Refuse to run as any release but the one the instance names, and refuse a vendored core newer than the checker or a pack it does not ship
- Hold every page to what its schema declares: the folder it sits in, its fields, its required sections, its enum values, its labels and the names it writes
- Fail a vendored file that is not as the tooling wrote it, naming the file on the commit that changed it
- Fail a change that alters an id already on the default branch
- Refuse a commit whose author is a seat of the governing instance that the phase named in its trailers does not list, and leave a person's commit, or one from outside the governing domain, unjudged
- Hold every Markdown file to one form, at the tool version the release pins
- Report every finding of a run together, name each type the vendored core carries no schema for, and say on every run that the writing rules were not checked

## Relationships

| Context | Pattern |
| --- | --- |
| Resolution | conformist |
| Vendoring | shared kernel |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/lib/checks.mjs |
| Implementation | https://github.com/companygraph/meta-model/blob/main/bin/check-instance.mjs |
| Implementation | https://github.com/companygraph/meta-model/blob/main/.github/workflows/instance-check.yml |
| The specification | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-09-10-instance-checks-design.md |
