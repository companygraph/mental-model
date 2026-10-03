---
id: 01a10042-5811-7dff-910b-5cbd7136f8b2
source: Local
kind: entity
---

# Run

> One following of a procedure against one instance, from the first question to the report, on behalf of the operator who asked for it. Everything it writes stays a proposal until the operator commits it.

## Attributes

| Attribute | Type | Description |
| --- | --- | --- |
| Mode | string | `Create` or `Update`, for a run that writes a profile or builds an instance |
| Operator | string | The person who asked for the run and decides what is theirs |
| Answers | list of string | Every question the operator answered, and the answer |
| Created | list of path | Every file the run wrote |
| Reused | list of string | The H1s of entities the run wrote against rather than created |
| Left out | list of string | Each fact no schema holds, named by its kind and never by its value |

## Relations

| Concept | Cardinality | As |
| --- | --- | --- |
| Procedure | one | follows |
| Reconciliation | many | |
| Consent record | many | |
| Agent pass | maybe one | |
| Ledger | maybe one | |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-profile/SKILL.md |
| Implementation | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-company/SKILL.md |
