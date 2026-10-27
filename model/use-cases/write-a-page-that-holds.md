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
realization: Main scenario released
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

## Realization

The plugin offers, while a reference is typed, the names the declaration's scope holds: a field's type, and for a row the owner named in the row (step 3; `test/scope.test.ts` tests the scope and `e2e/names.e2e.ts` the popup and the chosen name written, step 4). New entity creates the page under the type's folder with a fresh id, the H1 and the sections the schema requires (step 2; `e2e/entities.e2e.ts`, `src/freshid.ts`). A name that holds nothing is marked as an unresolved link when the line is left, before any check runs (3a; `e2e/editing-mark.e2e.ts`). The plugin checks the whole model on every change, bundles the meta-model checks at a pinned release and shows failures by file and rule (5a), and step 5's commit and the Check use case are the writer's. What is missing is a test that runs one page from the picker to a passing check; the e2e suite is not a required check and runs on a weekly schedule.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `e2e/names.e2e.ts` | satisfies | https://github.com/companygraph/obsidian-plugin/blob/0.34.0/e2e/names.e2e.ts |
| `e2e/editing-mark.e2e.ts` | satisfies | https://github.com/companygraph/obsidian-plugin/blob/0.34.0/e2e/editing-mark.e2e.ts |
| `test/scope.test.ts` | satisfies | https://github.com/companygraph/obsidian-plugin/blob/0.34.0/test/scope.test.ts |

## References

| What | URL |
| --- | --- |
| The editor plugin | https://github.com/companygraph/obsidian-plugin |
| The rules every page obeys | https://github.com/companygraph/meta-model/blob/main/core/CONVENTIONS.md |
