---
id: 01a13dc2-94f1-7a36-8756-8dfcd1fdcb88
source: Governance research
source-id: GD-02
kind: functional
modality: must
realization: Not released
---

# Any past state can be read whole

> Any state a model has had can be read whole, by its id, for as long as the model exists.

## Why

A site and a server draw the model at the state they pin, and a check compares a change with the state it started from; both read a state that is no longer the latest.

## Fit criterion

A state from a year before is read by its id, and the checker finds in it what it found then. Today a checkout of a commit meets it.

## Applies to

| Type | Entity |
| --- | --- |
| product | CompanyGraph Core |

## Realization

Reading a past state is git. The release reads states by commit in `ids --range` and `commits --range`, but it adds no store of past states; this is git's behavior and no released product meets it.
