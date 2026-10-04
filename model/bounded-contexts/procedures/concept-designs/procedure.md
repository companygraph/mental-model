---
id: 01a10042-58a6-7ce6-a96b-db5abe9289c3
source: Local
kind: entity
---

# Procedure

> One piece of judgment work written down for an agent to follow, shipped with a release of the tooling and installed where the agent the instance was made for reads it. A procedure the instance writes for itself sits beside these under another name and is not one of them.

## Attributes

| Attribute | Term | Type | Many | Description |
| --- | --- | --- | --- | --- |
| Name | | string | | The name the agent calls it by, `companygraph-profile` and its siblings |
| Agent | | string | | The agent it is written for |
| Work | | string | | What it does and why no script does it, in one paragraph |
| Allowed tools | | string | yes | What the agent may use while following it |

## Relations

| Concept | Cardinality | As |
| --- | --- | --- |
| Procedure | many | calls |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills |
