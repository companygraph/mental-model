---
id: 01a1312d-83b6-719e-bff9-46901f2c6476
source: Local
kind: functional
modality: must
realization: Released
---

# A model that does not resolve is not served

> A commit at which a page names something that resolves to nothing is served by no surface: no graph is drawn from it and no page is published from it.

## Why

A surface that served a broken model would hand a visitor a claim that leads nowhere, and the last commit that resolved is the better answer until the model is corrected.

## Fit criterion

A deployment built at a commit where a page names nothing draws no graph and serves nothing from that commit; and a site build at such a commit stops, says where the name was written and what it searched, and leaves the committed pages as they were.

## Applies to

| Type | Entity |
| --- | --- |
| feature | An agent reads the model |
| feature | The vocabulary on the web |

## Realization

The server's `buildSnapshot` calls the meta-model parser, which throws `R4: "<name>" in <where> names no <type>` for a name that resolves to nothing, and the deployment workflow runs the snapshot step before it builds the image, pushes it or applies Terraform, so a commit with such a page draws no graph and nothing from it is served; the previous image keeps serving. The site's `build/build.mjs` calls the same parser per target, and the parser's error names the value, where it was written and the type searched; the build writes a target's JSON only after its parse, and `build:check` in the site's `verify` job fails the same way, leaving the committed pages untouched. The parser's own tests check the throw, the quoted name and the type searched. No test feeds the snapshot build or the site build a page that names nothing and checks that nothing is written.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `lib/snapshot.mjs` | satisfies | https://github.com/companygraph/mcp-server/blob/v0.69.0/lib/snapshot.mjs |
| `.github/workflows/deploy-google.yml` | satisfies | https://github.com/companygraph/mcp-server/blob/v0.69.0/.github/workflows/deploy-google.yml |
| `build/build.mjs` | satisfies | https://github.com/companygraph/companygraph.github.io/blob/3f8e4a25f599cc0e3c77cce8cce17e585d7a6b0e/build/build.mjs |
| `verify/instance.test.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/instance.test.mjs |

## References

| What | URL |
| --- | --- |
| The site's build | https://github.com/companygraph/companygraph.github.io/blob/main/build/build.mjs |
