---
id: 01a10042-631a-71c6-a1c1-f3be52158c56
source: Local
refines: Checks an instance runs
contexts:
  - Checking
decisions:
  - Core is vendored into an instance at a release its manifest names
---

# An instance is checked only against the release it adopted

> The checker an instance's workflow calls is the release its manifest names, and it reads the schemas from the core that instance vendored, so a newer release never holds a model to rules it has not taken.

## Operational principle

When a new release of the checker ships, an instance whose manifest still names the old one is checked on its next change by the old one, against the schemas in its own vendored core, and passes or fails exactly as it did before; it meets the new rules only on the commit that moves its manifest and its workflow line together.

## Scenarios

### SC-K1: A checker that is not the named release

Given an instance whose manifest names one release of the tooling, when another release of the checker is run over it, then the run refuses before reading a page and says to move the pin and the workflow together, or to call the release the manifest names.

### SC-K2: A core newer than the checker

Given an instance whose manifest vendors a core newer than the checker it names, when the instance is checked, then the run refuses and says to move the manifest's tooling and the workflow pin to that core's release together.

### SC-K3: A core older than a type

Given an instance that vendored a core from before a type existed, when the instance is checked, then that type is reported as not checked, because its vendored core carries no schema for it, and the run does not fail for it.

### SC-K4: An edited vendored file

Given a file of the vendored core that someone edited inside the instance, when the instance is checked, then the run fails naming that file as not as the tooling wrote it, and says `companygraph upgrade --force` puts it back.

### SC-K5: A pack the checker does not ship

Given a manifest that takes a pack the named checker does not ship, when the instance is checked, then the run refuses by the pack's name and lists the packs it ships.

### SC-K6: A green run says what it left

Given an instance with no finding, when it is checked, then the run passes and still says that every schema's writing rules were not checked and are the agent pass's.

## Uses

| Type | Entity | Context |
| --- | --- | --- |
| concept-design | Tooling pin | Checking |
| concept-design | Run | Checking |
| concept-design | Finding | Checking |
| domain-event | Run refused | Checking |
| domain-event | Instance checked | Checking |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/bin/check-instance.mjs |
| Implementation | https://github.com/companygraph/meta-model/blob/main/.github/workflows/instance-check.yml |
