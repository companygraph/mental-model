---
id: 01a1312b-b473-701a-aa2f-6cca819bca4c
source: Local
level: user goal
scope: system
primary-actor: Owner
features:
  - An instance is made and kept from one command
  - An agent does the work no script can, by the skills an instance ships
includes:
  - Check a change against the schemas
realization: Released end to end
---

# Start a company's model

> The owner has a repository that is an instance: a vendored core, a manifest, the entities no instance can pass without, the agent's own files and a gate, and it passes its checks before a single fact is written.

## Stakeholders and interests

| Stakeholder | Interest |
| --- | --- |
| Owner | An instance that passes on its first day, with nothing in it the company did not write |
| Writer | A README in each root folder naming the schema its files are written against |
| Agent | The procedures of the release that made the instance, held to their hashes like the vendored core |

## Preconditions

- The folder does not exist, or holds no `meta/` folder of its own.

## Trigger

The owner runs the command from a release tag, with nothing after it.

## Main success scenario

| Step | Actor | Action |
| --- | --- | --- |
| 1 | Owner | Runs the command with nothing after it, which opens the menu, and picks Make a model |
| 2 | Owner | Names the company, the folder and the agent the instance is written for |
| 3 | System | Vendors core at the release that runs and records a hash per vendored file in the manifest |
| 4 | System | Writes the sources page and one page per singular type, each with an id of its own, and a README in the model and in each root type folder naming its schema |
| 5 | System | Writes the gate: a workflow pinned to the release of the checker the manifest names as its tooling |
| 6 | System | Writes the agent's own files and the procedures of the release under its skills folder, each hash recorded beside the vendored core's |
| 7 | System | Says to run the check whenever the folder changes, and the vault command to write it in Obsidian |
| 8 | Owner | Checks the folder, as Check a change against the schemas says, and it passes |

## Extensions

| Step | Condition | Handling |
| --- | --- | --- |
| 2a | The folder already holds a `meta/` folder of its own | Nothing is written, the refusal names `meta/` as already there, and the use case ends |
| 2b | The agent asked for is one the release does not write for | The command refuses, naming the agents it writes for, and writes nothing |
| 3a | A core tag is asked for whose core is newer than the release that runs | The command refuses before anything is written, since no checker could then run the instance |

## Minimal guarantees

- Nothing is written where the command refuses.
- A folder that already holds a model is left as it was.

## Success guarantees

- The instance passes the checks on its first day, with nothing in its model but the stubs.
- The manifest names the release that made the instance and a hash for every file it vendored.

## Realization

In meta-model v0.95.0 the menu entry Make a model asks the folder (and adds beside existing files only on a yes), the company's name and the gate, and the agent is claude, the one agent the release writes for, so it is not asked; this is the only difference from step 2 as the page words it. `init` vendors the release's core and records a sha256 per vendored file in the manifest (3), writes the sources page, the singular entities, a README in the model and in each root type folder (4), the workflow pinned to the release of the checker (5), `AGENTS.md`, `CLAUDE.md` and the skills with their hashes (6), and prints the check command and the vault command (7). Extensions: a folder that holds `meta/` or `.companygraph/` is refused naming it with nothing written (2a, `plan.test.mjs`), an agent it does not write for is refused by name (2b), and a core newer than the release is refused before anything is written (3a). The test `the menu makes an instance from answers alone, and what it made passes the checks` in `verify/cli.test.mjs` picks Make a model, answers the questions, and runs the check on the result with no failures; `an instance init writes passes the mechanical checks on its first day` and `what it wrote is what its manifest says it wrote` observe the two success guarantees (a pass on the first day, the release and a hash for every vendored file).

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `verify/cli.test.mjs` | verifies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/cli.test.mjs |
| `verify/plan.test.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/plan.test.mjs |

## References

| What | URL |
| --- | --- |
| The command-line specification | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-09-20-the-cli-design.md |
| The site's page on the command | https://companygraph.io/cli/ |
