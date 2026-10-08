---
id: 01a10042-577c-7e30-ae5b-e3dcd324bd8b
source: Local
kind: value object
refines: Agent pass
---

# Agent pass

> One validation of an instance as a report: the mechanical checks as they printed, every writing rule judged against every entity of its type, and what was not checked, so a clean report is never read as more than it is.

## Attributes

| Attribute | Term | Type | Many | Description |
| --- | --- | --- | --- | --- |
| Core version | | version | | The release of the rules the pass held the instance to |
| Mechanical failures | | string | yes | What the check printed, copied as it is |
| Findings | | string | yes | Each writing rule broken, in the rule's own words, with the file that breaks it |
| Gaps | | string | yes | Each skill a held seat requires and a human profile does not claim, outside the count of failures |
| Not checked | | string | yes | Everything the pass skipped, such as the mechanical checks where they could not run |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-validate/SKILL.md |
