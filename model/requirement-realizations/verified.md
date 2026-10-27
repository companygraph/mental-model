---
id: 01a17bea-82fe-74d4-9219-4ca297178fb8
source: Local
rank: 40
evidence: verifies
---

# Verified

> The latest release meets the requirement, and a test in that release observes what its fit criterion observes.

## What it means

A requirement is Verified when the latest release of the product it applies to meets it and at least one test in that release observes what its fit criterion observes, which an `## Evidence` row that `verifies` names at the release's tag. A repository that deploys rather than tags, as the site and its deployments do, is released at the commit it has deployed. A page enters the level when a release ships that test, and moves down to Released when a release drops the test or the test no longer observes the fit criterion, or lower when a release drops what meets it. Work that no release carries counts for nothing. While a requirement is Verified, a reader may rely on the release meeting it and may run the test to see that it still does.
