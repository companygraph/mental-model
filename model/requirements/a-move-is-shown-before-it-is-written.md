---
id: 01a1312d-d213-79b9-b25f-3ef12ecbec31
source: Local
kind: functional
modality: must
---

# A move is shown before it is written

> A move of an instance to another release lists every path it would write or remove, and writes only on a yes.

## Why

A move touches the vendored core, the packs and the procedures, and an owner who sees the list first can stop a move that would reach a file they did not expect; a move that wrote first would leave the owner reading a diff to find out what happened.

## Fit criterion

Move a model, picked on an instance on an older release, lists every path before writing one, and the instance is moved only on a yes to Go ahead.

## Applies to

| Type | Entity |
| --- | --- |
| feature | An instance is made and kept from one command |

## References

| What | URL |
| --- | --- |
| The command-line specification | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-09-20-the-cli-design.md |
