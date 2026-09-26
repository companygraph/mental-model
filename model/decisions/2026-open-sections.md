---
source: Local
decided: 2026-09-19
kind: Vocabulary
status: Standing
by: Owner
---

# A section is open and a field is closed

> A page may carry sections its schema does not declare, which are read as prose, and may not carry a frontmatter field its schema does not declare, which is an error.

## The question

Whether an instance may add to a page beyond what its schema declares, and where. It had to be decided in September 2026, when required sections were being held by the checker for the first time, because the checker needed to know whether an undeclared heading is a finding.

## Alternatives

| Option | Why not |
| --- | --- |
| Both closed | An instance could not carry a section of its own, and every local need would be a release of core. |
| Both open | A field left behind by a rename would render under the old name while every check reported green, which is the failure a closed field exists to prevent. |

## Why

A field left over by a rename still renders as though it were the field, while a section of the page's own claims to be nothing the schema knows. The two failures are not alike, so the two rules are not: a field resolves references and satisfies requirements, and must be declared; a heading resolves nothing and draws no edge, and may be the page's own.

## Consequences

An undeclared field is an error and a rename cannot half-happen; an undeclared heading is prose; an optional section written with a typo reads as one of the page's own, and only an editor that knows the schema can tell. What it gave up is the local field: an instance cannot carry one.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| concept | Schema | | changed it |

## References

| What | URL |
| --- | --- |
| The specification | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-09-19-required-sections-design.md |
