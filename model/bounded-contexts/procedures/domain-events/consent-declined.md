---
id: 01a10042-5909-705e-9a13-c94901f3c5c6
source: Local
emitted-by: Procedure run
---

# Consent declined

> A consent a source's use needed was not given, so the content that rested on it was not written, and the run proposed the line that records the decision for the next run.

## Payload

| Attribute | Type | Description |
| --- | --- | --- |
| Source | string | The source, by its H1 |
| Subject | string | The company, person or document whose consent was not given |
| Agent-file line | string | The line proposed for the instance's agent file, so the question is not asked again |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-consent/SKILL.md |
