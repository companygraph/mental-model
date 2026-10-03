---
id: 01a10042-612a-730a-ad10-1e5233131958
source: Local
root: Manifest
members:
  - Unit
  - Vendored file
decisions:
  - Core is vendored into an instance at a release its manifest names
---

# Manifest

> Every file the tooling vendored into a repository is recorded with the hash it was written with, at the one release the manifest and the workflow both name.

## Invariants

| Label | Invariant |
| --- | --- |
| INV-V1 | Every file written under a unit's folder or the skills folder is recorded in the manifest with the hash of its text, and the instance's own files are not. |
| INV-V2 | The manifest's tooling and the workflow's ref to the reusable check name the same release; making an instance writes both, and a move moves both, every ref of the workflow included; a repository with no such workflow is given none. |
| INV-V3 | The vendored core is never newer than the tooling; a core that is is refused before anything is written, naming the release to run instead. |
| INV-V4 | A move writes nothing while any recorded file is edited, missing or named outside the manifest's own units and skills, or while the units folder is not a plain relative path; `--force` overwrites an edited or missing one, never a path outside. |
| INV-V5 | A pack comes from the release that runs, so a pack is never vendored beside a core fetched from another tag. |
| INV-V6 | A refusal writes nothing: every file already in the way is found and named before the first is written. |
| INV-V7 | A file the repository owns, its agent files, seat hook, export inputs, `pins.json`, `.gitignore`, `.gitattributes` and language page, is written only where none is there and is never hashed or replaced. |
| INV-V8 | A manifest that names no core records no files, and nothing is vendored into its repository. |

## Handled commands

| Command | Description |
| --- | --- |
| Make an instance | Writes core, the packs asked for, the skills, the manifest, a README per root folder, the starting entities, the workflow and the agent's files into an empty folder, or beside a repository's files with `--here`; refuses a units folder or `.companygraph/` already there |
| Move an instance to a release | Writes what the release changed and removes what it dropped, takes a pack not taken before, then runs the check and says what the model owes; with `--dry-run` it lists what it would write and remove, and it refuses while the Markdown is out of the form unless forced |
| Adopt a repository | Writes a manifest with no core, the workflow that runs the form, the seat hook and a `pins.json` into a repository with no manifest; refuses one that has a manifest and points at the move |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/lib/plan.mjs |
| Implementation | https://github.com/companygraph/meta-model/blob/main/bin/companygraph.mjs |
