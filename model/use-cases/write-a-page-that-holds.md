---
id: 01a1312b-c453-7585-bcc7-1f4e34aa2446
source: Local
level: user goal
scope: system
primary-actor: Writer
features:
  - A vocabulary to describe a company in
  - Checks while a file is edited
includes:
  - Check a change against the schemas
---

# Write a page that holds

> The writer has a page that says one fact about the company in the type its schema declares, with every name on it resolving, before the change is pushed.

## Stakeholders and interests

| Stakeholder | Interest |
| --- | --- |
| Writer | What the schema requires, and what they broke, while they type rather than when the change is pushed |
| Owner | No page that names nothing reaches the default branch |
| Visitor | A model whose every reference resolves, so an answer can link what it rests on |

## Preconditions

- The instance is open as a vault with the plugin in it, which the vault command puts there.

## Trigger

A fact about the company is to be written down.

## Main success scenario

| Step | Actor | Action |
| --- | --- | --- |
| 1 | Writer | Picks the type the fact belongs to and reads its schema whole: the frontmatter table, the sections table and the writing rules |
| 2 | Writer | Writes the page under the type's folder with a fresh id, the H1 as its name, the tagline and the sections the schema requires |
| 3 | System | Offers, while a reference is typed, exactly the names the declaration's scope holds: a field's type, a row's owner |
| 4 | Writer | Picks the name offered |
| 5 | Writer | Commits the page on a branch and holds the change to the schemas, as Check a change against the schemas says |

## Extensions

| Step | Condition | Handling |
| --- | --- | --- |
| 3a | A name is typed that holds nothing in its scope | The editor marks it as an unresolved link when the line is left, before any check runs, and the writer corrects it |
| 5a | The check fails on the page | The failure names the file and the rule, the writer corrects the page, and the scenario goes on at 5 |

## Minimal guarantees

- A name that resolves to nothing is marked where it is written, before the change is pushed.
- No page reaches the default branch in a form its schema does not declare.

## Success guarantees

- The page passes the checks of the release the instance adopted.
- Every name on the page resolves to one entity of the type its declaration names.

## References

| What | URL |
| --- | --- |
| The editor plugin | https://github.com/companygraph/obsidian-plugin |
| The rules every page obeys | https://github.com/companygraph/meta-model/blob/main/core/CONVENTIONS.md |
