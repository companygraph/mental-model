---
source: Local
owner: Contributor
executed-by:
  - Contributor
gate-approvers:
  - Contributor
escalation-authority: Owner
gate-to: Consider
---

# Propose

> Offer the change, under the address the Contributor means to be known by.

## What it takes

The repository, its conventions and its schemas, all of which are published and need nobody's permission to read.

## Activities

1. The Contributor branches from the default branch and makes the change there.
2. The Contributor writes what is now true that was not before, as the pull request's description.
3. The Contributor commits under their own address, which is theirs to choose and nobody else's to set.
4. The Contributor opens the pull request and lets the check run.

## What it produces

| Deliverable | Description |
| --- | --- |
| Pull request | A change against the default branch, saying what is now true that was not, under its author's own address |

## What it never does

- Never commits under an address that is not the Contributor's own.
- Never merges, tags or releases; that is the Owner's and is not delegated.
- Never has to have read every convention first; where one was missed, naming it is the company's work.

## Gate

To leave Propose, all of these hold:

- A pull request exists against the default branch.
- It says what is now true that was not before.
- Its commits carry the address their author means to be known by.

Where they cannot be met, the Contributor decides whether to carry on or to stop; nothing here obliges anyone to finish what they started.
