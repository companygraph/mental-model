---
id: 01a13c5e-3775-7125-84d5-c4be1eedaf2c
source: Local
kind: preventive
mode: manual
enforces:
  - Nobody is asked which company a request comes from
performed-by: Owner
---

# A request is asked for its gap and never its company

> Whoever reads a request asks only for the entity, the field or the rule that was missing, never which company it comes from, and a name the asker offers stays out of everything made from it.

## How it is carried out

The Owner, in Understand, on every feature request: it reads the request as written, asks only for the gap where the request leaves it out, and restates it in the issue without the name of any company the asker offered. Where the request becomes vocabulary, the skill that writes the specification records the names the operator says to keep out, and before the specification is committed searches its diff and its commit message for each of them, after first showing that the same search finds the name in its own report, and refuses to commit until it finds none.

## Applies to

| Type | Entity | Owner |
| --- | --- | --- |
| phase | Understand | Feature request |

## References

| What | URL |
| --- | --- |
| The skill for new vocabulary | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-09-30-a-skill-for-new-vocabulary-design.md |
