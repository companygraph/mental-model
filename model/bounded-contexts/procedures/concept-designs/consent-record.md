---
id: 01a10042-57de-7f86-822b-ff29a4bcbe31
source: Local
kind: value object
---

# Consent record

> What a source's content may be used for and who agreed to it, kept as sentences in one fixed shape on the source every fact names. It records what the operator stated, and is no legal advice.

## Attributes

| Attribute | Term | Type | Many | Description |
| --- | --- | --- | --- | --- |
| Terms | | string | | What the content is published under, or "no stated terms" |
| Read on | | date | | When the terms were read |
| Who | | string | | The person who consented, for a consent given |
| Capacity | | string | | In what capacity they consented |
| Consented on | | date | | When |
| How | | string | | By mail, by a signed letter, in person, or an assumption the operator made for a test run |
| To what | | string | | The use consented to |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-consent/SKILL.md |
