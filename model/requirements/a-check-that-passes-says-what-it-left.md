---
id: 01a1312e-302d-7238-b694-50d430636faf
source: Local
kind: functional
modality: must
follows:
  - A check counts only when its output was seen
---

# A check that passes says what it left

> A run of the checks that finds nothing still says what it did not check: every schema's writing rules, and any type its vendored core carries no schema for.

## Why

A check counts only when its output was seen, and a green run read as more than it is would let a page pass that nothing read. The writing rules are the agent pass's, and a run that said nothing about them would be read as having checked them.

## Fit criterion

A run with no finding passes and says that every schema's writing rules were not checked and are the agent pass's; a type the vendored core predates is reported as not checked; and an agent that cannot run the mechanical checks names them under Not checked rather than applying them by hand.

## Applies to

| Type | Entity |
| --- | --- |
| feature | Checks an instance runs |

## References

| What | URL |
| --- | --- |
| The reading pass | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-validate/SKILL.md |
