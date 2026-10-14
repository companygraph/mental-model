---
id: 01a13b7f-fa1b-74f3-8ee2-8a56f2fe59b7
source: Local
kind: preventive
mode: automated
enforces:
  - A worktree is removed only once its plan is done
---

# An agent's hook refuses removing a worktree that holds a plan

> Before an agent on the Owner's machine runs a shell command, a hook refuses it where it would remove a worktree that still holds a plan's ledger.

## How it is carried out

A hook Claude Code runs on the Owner's machine before every shell command an agent issues: it reads each `git worktree remove` in the command, resolves the worktree's path through any `cd` or `-C` before it, and refuses the command where that worktree holds a plan's ledger under `.superpowers/sdd/`, saying why, so the agent stops before anything is deleted. It holds an agent and not the Owner's own terminal, and a worktree deleted some other way, such as by `rm -rf`, passes it; the hook lives in the Owner's own settings and in no repository.

## Applies to

| Type | Entity | Owner |
| --- | --- | --- |
| phase | Implement | Delivery |
| phase | Integrate | Delivery |

## References

| What | URL |
| --- | --- |
| Claude Code hooks | https://code.claude.com/docs/en/hooks |
