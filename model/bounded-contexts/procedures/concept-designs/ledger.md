---
id: 01a10042-5842-77cf-a02b-1a00e41b0b67
source: Local
kind: entity
---

# Ledger

> The operator's record of a run that builds an instance from a company's web address: every page read and when, every fact proposed with its address and the source's own words, and what was not read and why. It names people the operator may strike, so it is never part of the model and never committed.

## Attributes

| Attribute | Type | Description |
| --- | --- | --- |
| Date | date | The day of the run, in its file name |
| Rows | list of string | One table per type, one row per proposed entity or fact, with its address and the words the source uses |
| Further sources | list of string | What a search surfaced and the run did not read |
| Read for nothing | list of string | Pages read that yielded nothing |
| Not read | list of string | Pages not read, and why: a robots rule, a login, a paywall |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-company/SKILL.md |
