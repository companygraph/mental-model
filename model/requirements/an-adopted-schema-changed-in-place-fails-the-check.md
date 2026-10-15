---
id: 01a13dc2-94f1-77c5-bd14-dbce6627127f
source: Governance research
source-id: GD-25
kind: functional
modality: must
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
