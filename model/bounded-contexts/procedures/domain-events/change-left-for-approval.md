---
id: 01a10042-58d8-7ffb-819a-310722a178d8
source: Local
emitted-by: Procedure run
---

# Change left for approval

> A run wrote its pages, held them to the mechanical checks and the agent pass, and handed them to the operator uncommitted, with a report of everything it decided and everything it did not.

## Payload

| Attribute | Type | Description |
| --- | --- | --- |
| Created | list of path | Each file written |
| Reused | list of string | The H1s written against rather than created |
| Answers | list of string | Every question the operator answered, and the answer |
| Left out | list of string | Each fact no schema holds, by kind |
| Validation | Agent pass | The checks and the writing rules, with the gaps and what was not checked |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-profile/SKILL.md |
| Implementation | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-company/SKILL.md |
