---
id: 01a13dc2-94f1-75b7-9702-f61b6cf69db0
source: Governance research
source-id: GD-28
kind: functional
modality: must
follows:
  - A secret is never written into a repository
realization: Not released
---

# A change that carries a secret is refused

> A change that carries a secret is refused before it is stored.

## Why

A stored secret is published to everyone who can read the model, and from then on it can only be rotated.

## Fit criterion

A change carrying a key in a known form is refused, and a push past the refusal shows who made it and why. Today push protection meets it for the forms GitHub recognizes.

## Applies to

| Type | Entity |
| --- | --- |
| product | CompanyGraph Core |

## Realization

Secret refusal is GitHub's push protection. No release scans a change for secrets.
