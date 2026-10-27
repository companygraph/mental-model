---
id: 01a17bea-cf13-7f6f-9ada-fb0a093ac1ab
source: Local
rank: 20
evidence: satisfies
---

# Main scenario released

> Every step of the main success scenario is in the latest releases, and the use case is not yet released end to end.

## What it means

A use case is at Main scenario released when every step of its main success scenario is in the latest release of the product that takes it, which at least one `## Evidence` row names at the release's tag, and it stays at the level until every extension is released and a test in a release walks the scenario as well. A page enters the level when a release ships the last step, moves up to Released end to end when the last of the two ships, and moves down to Not released when a release drops a step. While a use case is at this level, a reader may rely on the goal being reached when nothing goes wrong, and not on what `## Realization` names as missing.
