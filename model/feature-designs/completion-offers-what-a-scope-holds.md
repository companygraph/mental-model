---
id: 01a10031-87d6-7890-8543-8a7ce090f165
source: Local
refines: Checks while a file is edited
contexts:
  - Resolution
decisions:
  - A reference resolves by its declared type, never by name alone
---

# Completion offers what a scope holds

> While a reference is typed, the editor offers exactly the names the declaration's scope holds, and marks a name that holds nothing there.

## Operational principle

Typing in a field or cell that a schema declares as a reference offers the canonical names of its type, and inside an owned type only those of the owner its row names.

## Scenarios

### SC-E1: A field offers its type

Given a field declared `ref → role`, when its value is typed, then the editor offers the roles' names and no other type's.

### SC-E2: A row offers its owner's names

Given a Uses row whose Type is concept-design and whose Context is Resolution, when its Entity cell is typed, then the editor offers only Resolution's concept designs.

### SC-E3: A name that names nothing is marked

Given a name typed that holds nothing in its scope, when the line is left, then it is marked as an unresolved link before any check runs.

## Uses

| Type | Entity | Context |
| --- | --- | --- |
| concept-design | Declaration | Resolution |
| concept-design | Scope | Resolution |
