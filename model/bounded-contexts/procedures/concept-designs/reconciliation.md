---
id: 01a10042-57ad-73f0-b4a3-46cd7f11a2e4
source: Local
kind: value object
---

# Reconciliation

> Where one fact read from a document or a page stands against the model, on an Update: already held, new, held differently or left out by a decision the instance's agent file records. It is shown to the operator before anything is written.

## Attributes

| Attribute | Type | Description |
| --- | --- | --- |
| Fact | string | The fact as read, with the document or address it came from |
| Standing | string | `already held`, `new`, `held differently` or `left out by decision` |
| Where held | string | The entity that holds it, for a fact already held or held differently |
| Versions | list of string | Both versions quoted, for a fact held differently |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-profile/SKILL.md |
