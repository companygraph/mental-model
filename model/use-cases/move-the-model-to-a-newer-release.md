---
id: 01a1312b-e30c-7c0e-bd3f-e03cb450beb8
source: Local
level: user goal
scope: system
primary-actor: Owner
features:
  - An instance is made and kept from one command
includes:
  - Check a change against the schemas
---

# Move the model to a newer release

> The owner has the instance on the release they chose, its vendored core, its packs and its procedures moved together, and saw every path the move would write before it wrote one.

## Stakeholders and interests

| Stakeholder | Interest |
| --- | --- |
| Owner | No edit of theirs overwritten without their word |
| Writer | Pages that still pass after the move, or release notes that say what to write |

## Preconditions

- The manifest names the release the instance is on.

## Trigger

A release ships whose notes say what it asks of an instance, and the owner decides to take it.

## Main success scenario

| Step | Actor | Action |
| --- | --- | --- |
| 1 | Owner | Reads the release's notes: what changed for an instance, what breaks and how to take it |
| 2 | Owner | Runs the command and picks Move a model |
| 3 | System | Lists every path the move would write or remove |
| 4 | Owner | Says Go ahead |
| 5 | System | Moves core, the packs the manifest lists and the procedures to the release, records their hashes, and moves the manifest's tooling and the workflow's pin together |
| 6 | Writer | Writes what the notes ask of an instance |
| 7 | Owner | Holds the moved instance to its schemas, as Check a change against the schemas says |

## Extensions

| Step | Condition | Handling |
| --- | --- | --- |
| 3a | A vendored file was edited inside the instance | Nothing is written and the file is named; moved with the force flag, it is overwritten and named as overwritten |
| 4a | The owner says no | Nothing is written and the use case ends |
| 5a | The instance keeps a procedure of its own under another name beside the shipped ones | The shipped procedures move and the instance's own is not touched |
| 7a | The check fails on a rule the release added | The writer writes what the rule asks in the same change, since a page that fails is not merged, and the scenario goes on at 7 |

## Minimal guarantees

- Nothing is moved that the owner was not shown first.
- The core vendored and the checker named stay a pair a checker can run.

## Success guarantees

- The manifest and the workflow name the release together, and the check at that release passes.

## References

| What | URL |
| --- | --- |
| The command-line specification | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-09-20-the-cli-design.md |
| The releases, each with its notes | https://github.com/companygraph/meta-model/releases |
