---
id: 01a1312e-2118-7f51-b253-d0e63d79b3b4
source: Local
kind: functional
modality: must
---

# Completion offers only the names the scope holds

> While a reference is typed, the editor offers exactly the names the declaration's scope holds: a field's type, and a row's owner where the row is scoped to one.

## Why

A name offered from the wrong type is a name the check will fail later; a completion that knows the declaration's scope cannot offer one, and the writer never has to know the vocabulary's folders to pick the right name.

## Fit criterion

A field declared as a reference to seats, when typed, offers the seats' names and no other type's; a row whose entity is scoped to an owner offers only that owner's names.

## Applies to

| Type | Entity |
| --- | --- |
| feature | Checks while a file is edited |

## References

| What | URL |
| --- | --- |
| The editor plugin | https://github.com/companygraph/obsidian-plugin |
