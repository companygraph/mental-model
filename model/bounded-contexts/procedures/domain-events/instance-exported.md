---
id: 01a10042-5873-7ed7-a508-ec888d5fd580
source: Local
emitted-by: Procedure run
---

# Instance exported

> The model was packaged from one walk as a skill archive for an agent and a bundle of sources for a notebook, and both were verified to carry every entity the model holds.

## Payload

| Attribute | Type | Description |
| --- | --- | --- |
| Skill archive | path | `dist/<skill>-skill.zip`, byte-identical across runs over an unchanged model |
| Notebook bundle | path | `dist/<instance>-gemini-notebook/` |
| Commit | commit hash | The commit the build read, marked when what it read was not yet committed |
| Core version | version | The core release the instance vendors |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-export/build.py |
| Verification | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-export/verify.py |
