---
source: Local
owner: Owner
executed-by:
  - Owner
gate-approvers:
  - Owner
escalation-authority: Owner
---

# Integrate

> Take the change into the default branch, and carry it to whoever vendors what it touched.

## What it takes

A change whose findings the Owner has ruled on, with one green check.

## Activities

1. The Owner merges with a merge commit, never a squash, so the address the contributor committed under reaches the default branch unchanged.
2. Where the change touches what another repository vendors or builds from, the Owner tags a release and writes its notes: a minor where a consumer re-syncs or re-pins, a major where it is asked to do more than either, and the notes say which.
3. The Owner moves every pin that names the release, each in a commit that says why, and every surface built from one of them is rebuilt at the commit it now names.
4. The Owner deletes the branch, as their own step.

## What it produces

| Deliverable | Description |
| --- | --- |
| Merge commit | The change on the default branch, carrying the author it was given |
| Release | Where something vendored moved: a tag and notes saying what a consumer must do |

## What it never does

- Never squashes, because a squash re-authors the commit to whoever pressed the button and a wrong identity would land looking correct.
- Never merges on a contributor's say-so that a check passed.
- Never leaves a pin that names a release the release has moved past.
- Never chains deleting the branch to the merge, because a failed merge would still delete it.

## Gate

To leave Integrate, all of these hold:

- The default branch carries the change under the address its author committed with.
- Where something vendored moved, a release exists and its notes say what a consumer must do.
- Every pin that names it has moved, or is recorded as deliberately behind.

Where they cannot be met, the Owner reverts rather than leaving the default branch in a state nobody chose.
