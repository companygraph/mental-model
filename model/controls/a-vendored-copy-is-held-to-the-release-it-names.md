---
id: 01a0ffcb-7af4-7c2c-b9d1-fdec394fdca6
source: Local
kind: detective
mode: automated
enforces:
  - A change to what another repository vendors is released
---

# A vendored copy is held to the release it names

> A pull request fails where what a repository vendors differs from the release it pins, so a change reaches another repository only once it is released.

## How it is carried out

The conventions job, required on the default branch of each of our repositories, on every pull request: `conventions-sync check` compares the vendored `conventions/` with the release `conventions.json` names and fails for each file that differs. In an instance, the instance check, also required, refuses a checker other than the release `.companygraph/manifest.json` names and fails where a vendored core file differs from the hash the manifest recorded when that release was taken. In the meta-model, `verify` fails where a tag sits on a commit whose package version is another, or where the instance check's ref is not that version, so a release cannot name a version it does not contain. Nothing checks what a release's notes ask of a consumer.

## Applies to

| Type | Entity | Owner |
| --- | --- | --- |
| phase | Integrate | Delivery |
| phase | Integrate | Contribution |

## References

| What | URL |
| --- | --- |
| The conventions job | https://github.com/robertblust/conventions/blob/main/.github/workflows/check.yml |
| The conventions copy check | https://github.com/robertblust/conventions/blob/main/conventions/conventions-sync |
| The instance check | https://github.com/companygraph/meta-model/blob/main/.github/workflows/instance-check.yml |
| The vendored core check | https://github.com/companygraph/meta-model/blob/main/bin/check-instance.mjs |
| The meta-model's release check | https://github.com/companygraph/meta-model/blob/main/verify/check.mjs |
