---
id: 01a13c5b-07ab-79ca-9235-fe766297ad4f
source: Local
kind: preventive
mode: manual
enforces:
  - A branch is deleted only after its merge is confirmed
performed-by: Implementer
---

# The Implementer reads the merge before deleting the branch

> A branch is deleted only after the Implementer has read its pull request as merged, in a step of its own.

## How it is carried out

The Implementer, at the end of Integrate, once a pull request it carried has been merged: it reads the pull request's state and its merge commit from GitHub in a command of its own, and only when the state reads merged removes the worktree, the local branch and the remote branch, each by name and each as a step of its own, never chained after the merge. A branch whose merge it cannot read stays. GitHub's own deletion of a merged branch is turned off in each of our repositories, so a branch goes only when this step takes it.

## Applies to

| Type | Entity | Owner |
| --- | --- | --- |
| phase | Integrate | Delivery |
| phase | Integrate | Contribution |

## References

| What | URL |
| --- | --- |
| Working rules | https://github.com/robertblust/conventions/blob/main/conventions/WORKING.md |
