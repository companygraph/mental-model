---
source: Local
owner: Reviewer
executed-by:
  - Reviewer
supported-by:
  - Contributor
  - Owner
gate-approvers:
  - Owner
escalation-authority: Owner
gate-to: Integrate
---

# Review

> Find what is wrong with the change, and hand it to whoever merges as findings rather than as a verdict.

## What it takes

A change the Owner has said is wanted, with its check reporting.

## Activities

1. The Reviewer reads the change against what the pull request says it does, and reports where the two disagree.
2. The Reviewer writes one finding per comment, each with a severity and the line it sits on.
3. The Reviewer judges what no check reads: whether an entity answers its schema's writing rules, and whether a text is in the register its place calls for.
4. The Reviewer says what it could not verify, rather than leaving a reader to assume it was checked.

## What it produces

| Deliverable | Description |
| --- | --- |
| Findings | One per comment, each with a severity and the line it sits on, addressed to whoever merges |

## What it never does

- Never merges, and never approves in a way that reads as merging.
- Never states a finding as a decision the contributor must take.
- Never counts a check nobody ran as a check that passed.
- Never asks for a change of taste as though it were a rule.

## Gate

To leave Review, all of these hold:

- Every finding carries a severity and the line it sits on.
- The Owner has read the findings and said which are to be acted on.
- What the review could not verify is written down.

Where they cannot be met, the Owner decides whether the change is narrowed, carried on by someone else, or declined.
