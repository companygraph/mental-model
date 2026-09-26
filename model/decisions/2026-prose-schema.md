---
source: Local
decided: 2026-08-23
kind: Vocabulary
status: Standing
by: Owner
---

# The schema written as prose is the only schema

> A type's schema is one Markdown file, read whole by an agent and in its fixed shape by a script, and no second schema exists for the script.

## The question

Whether the schemas are a stage on the way to a formal schema language or the working architecture of a model with hundreds of files. It had to be decided in the first specification, in August 2026, because every schema written after it would be written in one form or the other.

## Alternatives

| Option | Why not |
| --- | --- |
| A JSON Schema beside the prose | Two schemas drift, the one a script reads wins over the one a person reads, and the writing rules, which only a person can hold a page to, would live in neither. |
| A schema only a script reads | An agent reading a page would have nothing to hold it to but the script's output, and the thesis the model ships under, that with the right meta-model you describe the facts as Markdown, would be contradicted by its own schemas. |

## Why

The claim this model ships under is that a schema written as prose is the only schema, which an agent reads whole and a script reads where its shape is fixed. That holds only if the shape is checked, so the schema tables were written to one fixed shape and `verify` holds every schema to it; what a script cannot read, the writing rules, stays with the agent pass.

## Consequences

Every schema has the same columns, the same type vocabulary and the same word for required; a schema off the shape fails loudly; an instance is held to what its schema declares, and nothing beyond the schema decides which fields resolve. What it gave up is a machine-checkable schema for the prose half. It stays right for as long as the agent pass runs before every commit.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| concept | Schema | | made it |
| concept | Check | | changed it |

## References

| What | URL |
| --- | --- |
| The first specification | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-08-23-companygraph-design.md |
| The schemas made normative | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-09-08-schemas-are-normative-design.md |
