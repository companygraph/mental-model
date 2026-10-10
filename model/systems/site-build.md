---
id: 01a12578-5da5-7cf7-acaf-ee2a84eb1308
source: Local
kind: Deployment
owner: Owner
part-of: GitHub Actions
realizes:
  - The vocabulary on the web
---

# Site build

> Renders companygraph.io's pages from the vocabulary and the instance, each at a pinned commit, with the design package's renderer, for the seat that moves the pins, and checks on every pull request and every merge that the pages committed are the ones those commits render.

## Connects to

| System | As | Service | Carries | Via |
| --- | --- | --- | --- | --- |
| GitHub | the vocabulary's repository | | Schema | HTTPS |
| GitHub | the instance's repository | | Instance | HTTPS |
| GitHub | the design package | | | HTTPS |

## References

| What | URL |
| --- | --- |
| The site's source, with the build and its pins | https://github.com/companygraph/companygraph.github.io |
