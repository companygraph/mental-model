---
id: 01a10042-63e1-7050-969a-785fa035e567
source: Local
refines: An agent does the work no script can, by the skills an instance ships
contexts:
  - Procedures
  - Vendoring
  - Checking
decisions:
  - Claude is the first agent an instance supports, and not the only one
  - Core is vendored into an instance at a release its manifest names
  - The schema written as prose is the only schema
---

# An agent follows the procedures its release ships

> The procedures arrive in an instance with the release that made it, held to their hashes like the vendored core, so an agent asked for judgment work follows the one its instance names instead of improvising one.

## Operational principle

Before a commit, someone asks the agent to validate the instance; it runs the mechanical checks at the release the manifest names, copies what they print, judges every entity against its schema's writing rules, and ends its report with what it did not check.

## Scenarios

### SC-W1: init installs the procedures

Given `companygraph init` run for Claude, when it writes the instance, then every procedure of the running release is written under `.claude/skills/` and its hash recorded in the manifest beside the vendored core's.

### SC-W2: An agent the release does not write for

Given `init` asked for an agent the release does not write for, when it plans the instance, then it refuses, naming the agents it writes for, and writes nothing.

### SC-W3: A procedure edited in place

Given a shipped procedure edited inside the instance, when the instance is checked, then the check fails on that file and says `companygraph upgrade --force` puts it back.

### SC-W4: The instance's own procedure is left alone

Given an instance that keeps a procedure of its own under another name beside the shipped ones, when it is upgraded, then the shipped procedures move to the new release and its own is not touched.

### SC-W5: Checks that cannot run are not walked by hand

Given a machine with no network or no Node, when the agent validates the instance, then its report names the mechanical checks under Not checked and the agent does not apply those rules itself.

## Uses

| Type | Entity | Context |
| --- | --- | --- |
| concept-design | Procedure | Procedures |
| concept-design | Agent pass | Procedures |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/lib/plan.mjs |
| Implementation | https://github.com/companygraph/meta-model/blob/main/bin/check-instance.mjs |
| Implementation | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-validate/SKILL.md |
