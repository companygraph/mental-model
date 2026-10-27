---
id: 01a1312b-d3f8-707f-87ad-f0a8ed11d429
source: Local
level: user goal
scope: system
primary-actor: Writer
features:
  - Checks an instance runs
realization: Main scenario released
---

# Check a change against the schemas

> The writer knows, before a change lands, whether every page still holds to the schemas the instance adopted, and where not, which page and which rule.

## Stakeholders and interests

| Stakeholder | Interest |
| --- | --- |
| Writer | A failure that names the file and the rule |
| Owner | No release holds the model to rules the instance has not taken |
| Agent | A run that says which rules it left for the reading pass |

## Preconditions

- The manifest names the release of the checker and the core the instance vendored.

## Trigger

A change is pushed, or the writer runs the check from the instance root.

## Main success scenario

| Step | Actor | Action |
| --- | --- | --- |
| 1 | Writer | Runs the check at the release the manifest names, or pushes and the workflow calls it there |
| 2 | System | Reads the schemas from the core the instance vendored, not from the release that runs |
| 3 | System | Holds every vendored file to its hash, and every page's frontmatter, references, tables and ids to its schema |
| 4 | System | Passes, and says that every schema's writing rules were not checked and are the agent pass's |
| 5 | Agent | Reads each schema's writing rules against the pages the change touched, and reports what it judged and what it did not check |

## Extensions

| Step | Condition | Handling |
| --- | --- | --- |
| 1a | The checker run is not the release the manifest names | It refuses before reading a page and says to move the pin and the workflow together, or to call the release the manifest names |
| 1b | The manifest vendors a core newer than the checker | It refuses and says to move the manifest's tooling and the workflow pin to that core's release together |
| 1c | The manifest takes a pack the checker does not ship | It refuses by the pack's name and lists the packs it ships |
| 3a | A vendored file was edited inside the instance | The run fails naming the file as not as the tooling wrote it, and says the forced upgrade puts it back |
| 3b | A name on a page resolves to nothing | The run fails on that page, saying what the column or field is declared to reference and that it names no entity |
| 3c | A name on a page exists under another type | The run fails, saying the name is an entity of that type, and never resolves it there |
| 3d | The vendored core predates a type | That type is reported as not checked, and the run does not fail for it |
| 5a | The machine has no network or no Node | The agent names the mechanical checks under Not checked and does not apply those rules by hand |

## Minimal guarantees

- No page is held to a rule its vendored core does not carry.
- A run that passes still says what it left.

## Success guarantees

- Every mechanical rule the release names passed over the change as it now stands.
- The writing rules were read by an agent, and its report names what it skipped.

## Realization

In meta-model v0.95.0 `bin/check-instance.mjs` (also reached as `companygraph check`) reads the schemas from the core under the instance's `meta/core` and not from the release that runs (step 2), refuses before reading a page when the manifest names another tooling release (1a), when the vendored core is newer than the checker (1b, tested) and when the manifest takes a pack the checker does not ship (1c, tested). It holds every vendored file and skill to its recorded hash (3a, tested), runs the reference, table, id and frontmatter checks with a failure that names the page and the rule (3 and 3b), refuses a name that exists only under another type (3c, `instance-checks.test.mjs`), reports a type the vendored core lacks as not checked (3d), and on a pass prints that every `## Writing rules` is the agent pass's (4). The instance workflow calls the same checker at the pinned release. Step 5 is `agents/claude/skills/companygraph-validate/SKILL.md`, which says to name the mechanical checks under Not checked when there is no network or Node (5a) and ends the report with a Not checked list; the tests that name it only check that init writes it and hashes it. `verify/cli.test.mjs` runs init and then check and expects no failures, which walks steps 1 to 4, but no test observes the second success guarantee (the writing rules read by an agent), so I keep the page below Released end to end.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `bin/check-instance.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/bin/check-instance.mjs |
| `verify/cli.test.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/cli.test.mjs |
| `agents/claude/skills/companygraph-validate/SKILL.md` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/agents/claude/skills/companygraph-validate/SKILL.md |

## References

| What | URL |
| --- | --- |
| The checker | https://github.com/companygraph/meta-model/blob/main/bin/check-instance.mjs |
| The workflow an instance calls | https://github.com/companygraph/meta-model/blob/main/.github/workflows/instance-check.yml |
| The reading pass | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-validate/SKILL.md |
