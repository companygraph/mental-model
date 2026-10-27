---
id: 01a1312e-1130-7910-857a-3e4af9bfce31
source: Local
kind: quality
modality: must
realization: Released
---

# A broken reference is marked when the line is left

> A name typed that holds nothing in its scope is marked as an unresolved link when the writer leaves the line, before any check runs.

## Why

A writer told at push time that a name was wrong has left the page and the thought; told as they leave the line, they fix it while the thought is still there.

## Fit criterion

A name typed that holds nothing in its scope is marked when the line is left, with no check run and no file pushed.

## Applies to

| Type | Entity |
| --- | --- |
| feature | Checks while a file is edited |

## Realization

A name a schema declares as a reference that resolves to nothing in its scope is drawn with the class `companygraph-ref is-unresolved`, in Source mode, in the Properties widget and in a table in Live Preview, with no check run and nothing pushed. The decoration is rebuilt on every document change, so a name is marked while it is typed and not only when the line is left, which is earlier than the criterion asks and means a half-typed name is marked too; an optional reference that names nothing is drawn as plain text and not marked. A test checks that the resolver returns nothing for an unknown name, for a name of another type and for another owner's name, which is what the mark rests on; no test runs the editor decoration.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `src/namelinks.ts` | satisfies | https://github.com/companygraph/obsidian-plugin/blob/0.34.0/src/namelinks.ts |
| `test/references.test.ts` | satisfies | https://github.com/companygraph/obsidian-plugin/blob/0.34.0/test/references.test.ts |

## References

| What | URL |
| --- | --- |
| The editor plugin | https://github.com/companygraph/obsidian-plugin |
