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
realization: Released end to end
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

## Realization

The menu entry Move a model in meta-model v0.95.0 runs `upgrade --dry-run` and prints `write` lines for every path the move would write (step 3), asks Go ahead and on a yes runs `upgrade`, which moves core, the packs the manifest lists and the skills, records their hashes and moves the manifest's tooling and the workflow pin together (5); a no ends with nothing written (4a, code only). `upgrade` refuses and names a vendored file edited inside the instance, and `--force` overwrites it and says so (3a, tested), refuses a core newer than itself with nothing written, and runs the check afterward, saying the upgrade stands and how many problems are the model's to fix (7 and 7a). A skill of the instance's own under a name the release does not write is left alone, and one under a name it would write is refused unless forced (5a, tested for the second case; the first follows from the delete list being the manifest's). The walking test is `upgrade moves an instance between two real releases end to end` in `verify/cli.test.mjs`: it sets an instance back to an older core, runs `upgrade`, and expects the new core, every recorded hash, the tooling, `core.version`, the workflow line and a passing check, which are the page's success guarantee. It calls `upgrade` and not the menu, which is why the confidence is medium.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `verify/cli.test.mjs` | verifies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/cli.test.mjs |
| `bin/companygraph.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/bin/companygraph.mjs |

## References

| What | URL |
| --- | --- |
| The command-line specification | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-09-20-the-cli-design.md |
| The releases, each with its notes | https://github.com/companygraph/meta-model/releases |
