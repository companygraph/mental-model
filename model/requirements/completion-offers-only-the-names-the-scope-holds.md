---
id: 01a1312e-2118-7f51-b253-d0e63d79b3b4
source: Local
kind: functional
modality: must
realization: Verified
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

## Realization

While a reference is typed, the candidate list is built from the declared type's names. A test types into the profile's `seats` field and checks it offers only the two seats and no other type's name. For a question's `Rests on` rows a test checks that the Entity cell offers the row's type within the row's owner, offers nothing while an owned type has no owner, and that the Owner cell offers the owning type's names; a pack note's owned type stays within its context. The Properties widget and tables complete in Live Preview through the same candidates; the widget itself runs only in Obsidian and I did not find a test of it.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `test/candidates.test.ts` | verifies | https://github.com/companygraph/obsidian-plugin/blob/0.34.0/test/candidates.test.ts |
| `src/candidates.ts` | satisfies | https://github.com/companygraph/obsidian-plugin/blob/0.34.0/src/candidates.ts |

## References

| What | URL |
| --- | --- |
| The editor plugin | https://github.com/companygraph/obsidian-plugin |
