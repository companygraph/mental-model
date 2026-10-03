---
id: 01a10042-60fa-7013-bc65-786c99bebd24
source: Local
classification: supporting
realizes:
  - Core
decisions:
  - Core is vendored into an instance at a release its manifest names
  - A release is its tag, and nothing we make is published to a registry
---

# Vendoring

> Brings core and the packs an instance takes into it at one release, records every file it wrote with its hash and moves them only when the instance asks. Whether the pages written beside them keep the rules is left to Checking.

## Responsibilities

- Make an instance in an empty folder, or beside a repository's own files, with core, its packs and the agent's skills vendored at the release that runs, a folder for each root type and the entities no instance passes without
- Record in the manifest the release the instance runs, the core it vendors with where that came from and a hash for every file it vendored
- Move an instance to a release only when asked, its core, packs, skills, manifest and workflow ref together, and refuse the whole move when a vendored file is not as it was written
- Write the files an instance owns, its agent files, seat hook, export inputs, pins and language page, only where none is there, and never replace one
- Give a repository that holds no model the manifest, the form's workflow, the seat hook and its pins, and move its release as an instance's is moved
- Say for each pin a repository declares or holds whether its upstream has moved on, and move none
- Give every page written before ids existed an id stamped with the moment its file was first committed

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/lib/plan.mjs |
| Implementation | https://github.com/companygraph/meta-model/blob/main/lib/instance-files.mjs |
| Implementation | https://github.com/companygraph/meta-model/blob/main/lib/pins.mjs |
| The tooling specification | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-08-25-companygraph-tooling-design.md |
| The machinery outside the family | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-10-01-the-machinery-outside-the-family-design.md |
