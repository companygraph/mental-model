---
id: 01a17bea-922c-7f68-9b5f-8f3c0fc4c8e1
source: Local
rank: 30
evidence: satisfies
---

# Released

> The latest release meets the requirement, and no test in that release observes its fit criterion yet.

## What it means

A requirement is Released when the latest release of the product it applies to meets all of it, which at least one `## Evidence` row names at the release's tag, while no test in that release observes what its fit criterion observes. A test that covers part of it is a row that satisfies. A page enters the level when a release ships the last missing part, moves up to Verified when a release ships such a test, and moves down to Partly released when a release drops part of it. While a requirement is Released, a reader may rely on the release behaving so, and not on a test catching the day it stops.
