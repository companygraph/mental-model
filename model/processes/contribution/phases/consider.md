---
source: Local
owner: Owner
executed-by:
  - Owner
supported-by:
  - Contributor
gate-approvers:
  - Owner
escalation-authority: Owner
gate-to: Review
---

# Consider

> Establish what the change is for, before anyone spends time on how it is written.

## What it takes

A pull request against the default branch, from anyone, with a description saying what is now true that was not before.

## Activities

1. The Owner reads the description before the diff, because a change whose purpose is unclear cannot be reviewed for whether it achieves it.
2. The Owner establishes whether the change is wanted at all, and says so early; a review of something that will not be taken spends a contributor's evening for nothing.
3. The Owner names which rules it will be held to, where the contributor may not know them — the register a text is written in, the form the Markdown takes, the schema an entity answers to.
4. The Owner checks that the status check reports, and that it is the contributor's own commit under their own address.

## What it produces

| Deliverable | Description |
| --- | --- |
| Accepted purpose | A statement that the change is wanted, or that it is not and why, written in the pull request |

## What it never does

- Never reviews the writing of a change it has not decided is wanted.
- Never asks a contributor to commit under an address that is not theirs.
- Never leaves a contributor to discover a rule from a failing check that could have been named.

## Gate

To leave Consider, all of these hold:

- The pull request says what is now true that was not before.
- The Owner has said the change is wanted.
- The status check has reported.

Where they cannot be met, the Owner says which of them failed and closes the pull request, with what would make a later one succeed.
