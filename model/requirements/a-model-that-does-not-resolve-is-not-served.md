---
id: 01a1312d-83b6-719e-bff9-46901f2c6476
source: Local
kind: functional
modality: must
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

## References

| What | URL |
| --- | --- |
| The site's build | https://github.com/companygraph/companygraph.github.io/blob/main/build/build.mjs |
