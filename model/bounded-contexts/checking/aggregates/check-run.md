---
id: 01a10042-5d16-7600-aa84-b9739571a03f
source: Local
root: Check run
members:
  - Check
  - Finding
  - Vocabulary
  - Tooling pin
decisions:
  - Core is vendored into an instance at a release its manifest names
  - The schema written as prose is the only schema
---

# Check run

> A run holds an instance only to the rules it adopted, as the release it named, and its report says everything it found and everything it did not check.

## Invariants

| Label | Invariant |
| --- | --- |
| INV-K1 | A run reads schemas only from the core and packs vendored in the instance, never from the checker's own core. |
| INV-K2 | A run whose checker release differs from the tooling pin refuses before it reads a page, naming both releases. |
| INV-K3 | A run refuses a vendored core newer than its checker release; a vendored core older than it is checked. |
| INV-K4 | A run refuses, by name, a pack the manifest takes that the checker does not ship. |
| INV-K5 | Every file whose hash the manifest records is in the instance and hashes to that value, or the run fails naming it. |
| INV-K6 | A finding never ends a run: every check runs, and every finding is reported together. |
| INV-K7 | Every type the vendored units carry no schema for is named in the report as not checked. |
| INV-K8 | Every report, passing or failing, says the writing rules were not checked. |
| INV-K9 | A run passes only when it has no finding. |
| INV-K10 | A commit by a seat of the governing instance names one process and one phase of it, and one of its tracks where the process runs on tracks, and the phase's executed-by lists the seat; a commit by a person of the instance or by an address outside its domain is not judged. |

## Handled commands

| Command | Emits | When | Description |
| --- | --- | --- | --- |
| Check an instance | | | Holds every page to the vendored schemas and every recorded file to its hash; refuses when the pins disagree, the core is newer or a pack is unknown |
| Check the form | | | Holds every Markdown file to the one form at the pinned tool version; refuses when the tooling pin names another release, unless asked to fix |
| Check a range of ids | | | Fails every page a range of commits modified or renamed whose id differs from the one it carried at the base |
| Check a range of commits | | | Judges every commit of a range, or one message before it is committed, against the seats, processes, phases and tracks the governing instance declares, and refuses one whose seat the named phase does not list |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/bin/check-instance.mjs |
| Implementation | https://github.com/companygraph/meta-model/blob/main/lib/checks.mjs |
| Implementation | https://github.com/companygraph/meta-model/blob/main/lib/seats.mjs |
