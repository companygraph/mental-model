---
id: 01a10042-574b-7664-bb48-61c561e4b429
source: Local
root: Procedure run
members:
  - Reconciliation
  - Consent record
  - Agent pass
  - Ledger
decisions:
  - Agents write the model, and a person approves every change to it
---

# Procedure run

> What a run writes into an instance is only what a schema holds, the operator kept and a consent allows, checked before it is handed back, and never committed by the run.

## Invariants

| Label | Invariant |
| --- | --- |
| INV-W1 | Nothing a run produces is committed by it: pages are written and validated and the commit is the operator's, and what it builds under `dist/` stays out of git. |
| INV-W2 | A level, a seat and a sentence in a person's or a company's own voice are proposed to the operator and shown as drafts, never settled by the run. |
| INV-W3 | A fact no schema has a place for is neither written into the model nor noted anywhere, and the report names it by its kind, never by its value. |
| INV-W4 | A fact that fits an entity the model holds is written against that entity by its H1, never under a second spelling. |
| INV-W5 | Content whose consent is needed and not given is not written: a declined person's rows are dropped, and where the company's consent or the profiled person's is declined, the run writes nothing but its report. |
| INV-W6 | On an Update every sentence already written is kept, and a fact held differently is shown with both versions before anything is written. |
| INV-W7 | Every page a run writes opens with a fresh id, never copied from another page, and a page that has one keeps it. |
| INV-W8 | A run that writes pages ends with the mechanical checks and the agent pass, and a repair that would change what the operator decided is asked, not made. |
| INV-W9 | A ledger is written only where git ignores it. |

## Handled commands

| Command | Description |
| --- | --- |
| Build an instance from a web address | Reads what the company publishes, puts the ledger to the operator and writes what was kept; on an Update it stops when the address is a different company |
| Write a profile from documents | Reads a folder of a person's documents and writes or extends their profile; on an Update it stops when the documents describe a different person |
| Record a source's terms and consent | Writes the terms found and each consent the operator states onto one source; it infers no consent the operator cannot state |
| Validate an instance | Runs the mechanical checks at the release the manifest names, then judges every writing rule; where the checks cannot run it says so rather than walking them by hand |
| Produce a surface | Writes one surface's content by the rules its page records; a request naming no surface against a model holding several is asked, not chosen |
| Export the instance | Builds the agent's skill archive and the notebook bundle from one walk and verifies both against the model |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills |
