---
id: 01a13dc2-94f1-7d4b-9185-87bb28e1832d
source: Local
source-id: GD-31
kind: functional
modality: must
follows:
  - The model is corrected first
---

# A published page is checked against the state it names

> Every page published from a model is checked against what the state it names would draw.

## Why

A page edited by hand, or drawn from another state, says something the model does not, and the model is corrected first and the page drawn again.

## Fit criterion

A page whose content differs from what its named state draws fails its site's check. Today `pages:check` and `build:check` in each site's required `verify` job meet it.

## Applies to

| Type | Entity |
| --- | --- |
| feature | The vocabulary on the web |
