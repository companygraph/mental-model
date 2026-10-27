---
id: 01a1312d-f16d-75d5-8b22-03bed2242fd5
source: Local
kind: constraint
modality: must
realization: Released
---

# A check reads nothing but the instance

> The checks over an instance read the instance's files and nothing else: no network, no filesystem beyond what they are handed, and no module but the readers they share with the parser.

## Why

The same checks run in a site's build, in the instance's workflow and in the tooling's own suite, and they give the same findings everywhere only when nothing outside the files they are handed can change the answer.

## Fit criterion

The checker's functions take a map of path to text and make no network call; the same instance checked in its workflow and in a site's build at the same release gives the same findings.

## Applies to

| Type | Entity |
| --- | --- |
| feature | Checks an instance runs |

## Realization

`checkInstance` in `lib/checks.mjs` takes a map of path to text (bytes for an image) and imports only `lib/instance.mjs`, `lib/ids.mjs` and `lib/localization.mjs`, the readers the parser also uses; it has no network call, no filesystem import and no `fetch`. The schemas come from the map under the instance's vendored core, never from the package. The command wrapper `bin/check-instance.mjs` builds that map from the instance's folders and, beside it, reads the files the manifest names from disk to compare hashes (the skills sit outside the folders it walks) and reads `judge/known.md` through `lib/history.mjs`, which imports `child_process`. That wrapper reads only the instance and its manifest-named files, but it is wider than the pure function the fit criterion names. No test in the release asserts that the checker makes no network call or that a workflow run and a site build give the same findings. `verify/consumer.test.mjs` installs the packed tarball into an empty project and runs `checkInstance` on a fixture graph, which shows the checker works as a consumer takes it, not that the findings are equal.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `lib/checks.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/lib/checks.mjs |
| `bin/check-instance.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/bin/check-instance.mjs |
| `verify/consumer.test.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/consumer.test.mjs |

## References

| What | URL |
| --- | --- |
| The meta-model, with what the checks are | https://github.com/companygraph/meta-model |
