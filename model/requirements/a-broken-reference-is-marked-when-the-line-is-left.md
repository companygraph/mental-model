---
id: 01a1312e-1130-7910-857a-3e4af9bfce31
source: Local
kind: quality
modality: must
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

## References

| What | URL |
| --- | --- |
| The editor plugin | https://github.com/companygraph/obsidian-plugin |
