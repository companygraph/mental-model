---
id: 01a1312b-f25e-7c08-8a9b-e82807ad3ba8
source: Local
level: user goal
scope: system
primary-actor: Owner
features:
  - A company of more than one person describes its units and who answers to whom
  - A company that builds software describes how it designs it
  - A company that runs systems describes its landscape
  - An instance is made and kept from one command
includes:
  - Move the model to a newer release
  - Write a page that holds
realization: Released end to end
---

# Take a pack the company needs

> The owner has the vocabulary a company of their kind needs, of more than one person, building software or running systems, vendored beside core and checked with it, without a second init.

## Stakeholders and interests

| Stakeholder | Interest |
| --- | --- |
| Owner | No empty folder implying the company forgot something it never had |
| Writer | A README in each folder the pack adds, naming the schema its files are written against |

## Preconditions

- The pack is one the release the instance is on ships.

## Trigger

The company has a kind of knowledge core has no type for at all, and a pack holds it.

## Main success scenario

| Step | Actor | Action |
| --- | --- | --- |
| 1 | Owner | Reads the pack's README: what each type is, the sources it draws on and where it departs from them |
| 2 | Owner | Moves the instance with the pack named, as Move the model to a newer release says |
| 3 | System | Vendors the pack as a unit beside core, lists it in the manifest, and gives each root folder it adds a README once |
| 4 | Writer | Writes the pages the pack's types hold, as Write a page that holds says |

## Extensions

| Step | Condition | Handling |
| --- | --- | --- |
| 2a | The pack is one the checker does not ship | The command refuses by the pack's name and lists the packs it ships |
| 2b | A core tag is named beside the pack | The command refuses, since a pack is released with its core, and the move is made without a core tag |

## Minimal guarantees

- A README the pack's folder was given is the instance's own from then on, and no later move rewrites it.
- No core page changes for a pack taken, since every edge from a pack's types to core's is optional.

## Success guarantees

- The pack's types are checked with core at the same release.

## Realization

In meta-model v0.95.0 `upgrade --pack <name>` (the menu's Move a model with a pack named, and `init --pack`) vendors the pack as a unit under `meta/<pack>/`, lists it in the manifest's `packs`, makes the pack's root folders and writes each folder's README only where the instance has none (steps 2 and 3; `plan.mjs` writes a README once and leaves one that is there). `upgrade --pack landscape` on an instance that took organization lists both and the check passes. A pack the release does not ship is refused by name with the packs it ships (2a, `packOfThisRelease`), and `--core` beside a pack is refused before anything is fetched (2b, tested). The check holds the pack's types against the pack's schemas at the same release as core (`packs.test.mjs`, `init --pack` tests), and the pack types name core's only through optional edges (guarantee, held by `packs.test.mjs`). The nearest walk is `upgrade --pack landscape on an instance that took organization lists both` in `verify/cli.test.mjs`, together with the three `init --pack ... passes check` tests; steps 1 and 4 are done by people.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `verify/cli.test.mjs` | verifies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/cli.test.mjs |
| `verify/packs.test.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/packs.test.mjs |

## References

| What | URL |
| --- | --- |
| The packs, each with its README | https://github.com/companygraph/meta-model/tree/main/packs |
