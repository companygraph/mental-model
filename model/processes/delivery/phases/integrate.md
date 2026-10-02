---
id: 01a0c202-d668-7e1a-b698-ec58b8cdf4b2
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
3. The Owner reads the diff and, where a surface carries the change, the rendered page, and gives the word; the merge follows, with a merge commit.
4. Where the change touches what another repository vendors or builds from, a release is tagged on the Owner's word, with notes the Owner has read: a minor where a consumer re-syncs or re-pins, a major where it is asked to do more than either, and the notes say which.
5. The Owner moves every pin that names the release, each in a commit that says why, and every surface built from one of them is rebuilt at the commit it now names.
6. The Owner deletes the branch and its worktree, as their own step.

## What it produces

| Deliverable | Description |
| --- | --- |
| Merged change | On the default branch, with its checks green |
| Release | Where one is due: the tag, notes saying whether a consumer re-syncs, re-pins or does more, and every pin that names it moved |
| Rebuilt surface | Where a surface is built from what changed: rebuilt at the commit it names, so the page and the model agree |

## What it never does

- Never leaves a consumer pinned to a release that no longer exists.

## Gate

Integrate is the last phase. The work is done when all of these hold:

- The checks pass on the pull request.
- It is merged on the Owner's word.
- Where a release was due it is tagged, and its notes say whether a consumer re-syncs, re-pins or does more.
- Every pin that names the release has moved with it, or is recorded as deliberately behind, and every surface built from one of them has been rebuilt.

## If not met

| Outcome | Leads to |
| --- | --- |
| release held | Integrate |
| reverted | |
