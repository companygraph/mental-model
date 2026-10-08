---
id: 01a10031-6925-7b3c-8f04-87b19b4f6103
source: Local
refines: Checks an instance runs
contexts:
  - Resolution
decisions:
  - A reference resolves by its declared type, never by name alone
---

# A name that names nothing is reported where it is written

> The check reads every name a schema declares as a reference, and reports each one that resolves to nothing, with the type it searched.

## Operational principle

When a page names an entity that does not exist under the type its field declares, the check fails on that page and says which type it searched, before the change can land.

## Scenarios

### SC-C1: A name that exists nowhere

Given a concept design whose Relations row names «Declarations», when the instance is checked, then the check fails on that page, saying the column is declared `ref → concept-design` and names no entity.

### SC-C2: A name under another type

Given a decision whose `by` names a person's profile rather than a seat, when the instance is checked, then it fails, saying the name is an entity of type profile, not seat, and never resolves it to the profile.

### SC-C3: A name inside its owner

Given two bounded contexts that each own a concept design called Graph, when a row names Graph in one context, then it resolves inside that context, and the other Graph is not considered.

## Uses

| Type | Entity | Context |
| --- | --- | --- |
| concept-design | Declaration | Resolution |
| concept-design | Scope | Resolution |
| domain-event | Name found unresolvable | Resolution |
