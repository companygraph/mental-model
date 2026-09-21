---
source: Local
owner: Owner
executed-by:
  - Controller
  - Reviewer
  - Owner
gate-approvers:
  - Owner
escalation-authority: Owner
---

# Integrate

> Put the change where it binds, release what other repositories take from it, and move everything that names it.

## What it takes

A branch that left Implement with its checks green, and the specification it was made from.

## Activities

1. The Reviewer reviews the whole branch against the specification, not task by task.
2. The Controller opens the pull request and stops.
3. The Owner reads the diff and, where a surface carries the change, the rendered page, and merges it with a merge commit.
4. Where the change touches what another repository vendors or builds from, the Owner tags a release and writes its notes: a minor where a consumer re-syncs or re-pins, a major where it is asked to do more than either, and the notes say which.
5. The Owner moves every pin that names the release, each in a commit that says why, and every surface built from one of them is rebuilt at the commit it now names.
6. The Owner deletes the branch and its worktree, as their own step.

## What it produces

| Deliverable | Description |
| --- | --- |
| Merged change | On the default branch, with its checks green |
| Release | Where one is due: the tag, notes saying whether a consumer re-syncs, re-pins or does more, and every pin that names it moved |
| Rebuilt surface | Where a surface is built from what changed: rebuilt at the commit it names, so the page and the model agree |

## What it never does

- Never merges without the Owner; an agent opens and reports.
- Never squashes a merge, because a squash re-authors the commit to whoever pressed the button and a wrong identity would land looking correct.
- Never chains a branch delete after a merge, because a failed merge would still run the delete and close the pull request.
- Never changes what another repository vendors without a release, because the change has made every copy of it stale.
- Never leaves a consumer pinned to a release that no longer exists.
- Never releases a change the model disagrees with.

## Gate

Integrate is the last phase. The work is done when all of these hold:

- The checks pass on the pull request.
- The Owner has merged it.
- Where a release was due it is tagged, and its notes say whether a consumer re-syncs, re-pins or does more.
- Every pin that names the release has moved with it, and every surface built from one of them has been rebuilt.

Where they cannot be met, the Owner decides whether the change is reverted or the release held.
