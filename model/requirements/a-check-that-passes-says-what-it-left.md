---
id: 01a1312e-302d-7238-b694-50d430636faf
source: Local
kind: functional
modality: must
follows:
  - A check counts only when its output was seen
realization: Released
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

## Realization

A run of `bin/check-instance.mjs` that finds nothing prints the pass line, then always prints `not checked: every ## Writing rules in every schema — that is the agent pass, R0`, and prints a second `not checked:` line naming each type for which the vendored core carries no schema. `checkInstance` returns that list as `skipped`. The `companygraph-validate` skill tells the agent to name the mechanical checks under Not checked when they cannot run (no network, no Node) and not to walk the rules by hand, and to end every report with a Not checked line. A test (`a type the vendored core does not carry is named, not passed over in silence`) observes the skipped list. No test reads the printed writing-rules line, and the agent clause is an instruction in a skill that no test exercises.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `bin/check-instance.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/bin/check-instance.mjs |
| `agents/claude/skills/companygraph-validate/SKILL.md` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/agents/claude/skills/companygraph-validate/SKILL.md |
| `verify/instance-checks.test.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/instance-checks.test.mjs |

## References

| What | URL |
| --- | --- |
| The reading pass | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-validate/SKILL.md |
