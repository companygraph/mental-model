---
id: 01a13dc2-94f1-77c5-bd14-dbce6627127f
source: Governance research
source-id: GD-25
kind: functional
modality: must
realization: Verified
---

# An adopted schema changed in place fails the check

> A schema changed inside an instance after the instance adopted it fails the instance's check.

## Why

An instance is held to the release it adopted only while its copy of that release is the release, and a schema edited in place would hold the model to rules nobody released.

## Fit criterion

One character changed in an adopted schema makes the check fail and name the file. Today the hash per file in the manifest, compared on every run, meets it.

## Applies to

| Type | Entity |
| --- | --- |
| feature | Checks an instance runs |

## Realization

`init` records a sha256 per vendored core file in `.companygraph/manifest.json`, and `bin/check-instance.mjs` compares every recorded file on each run, failing with `<path>: not as the tooling wrote it, and it is not the instance's to edit` or `named in .companygraph/manifest.json and not in the instance`. A test appends one line to the vendored `CONVENTIONS.md` and deletes `LICENSE`, and asserts that `check` exits 1 naming both files; another asserts that each recorded hash matches the written file. The tests do not edit a `*-schema.md` file or change a single character, but schemas go through the same loop. Line-end differences are normalized before hashing (a separate test).

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `verify/cli.test.mjs` | verifies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/cli.test.mjs |
| `bin/check-instance.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/bin/check-instance.mjs |
