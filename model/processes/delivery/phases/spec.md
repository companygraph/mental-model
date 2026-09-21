---
source: Local
owner: Specifier
executed-by:
  - Specifier
supported-by:
  - Writer
gate-approvers:
  - Owner
escalation-authority: Owner
gate-to: Plan
---

# Spec

> Write what the change must do, completely enough that nobody downstream has to guess.

## What it takes

A classified request, the model and the vocabulary the change must not contradict, and whatever it will touch, read rather than remembered.

## Activities

### Code

1. The Specifier reads the model, the vocabulary and the code the change lands in, before proposing anything.
2. The Specifier names the approaches worth considering, with their trade-offs, and recommends one.
3. The Specifier writes the specification: the gap, the decisions and their reasons, what was rejected and why, and what is explicitly not being done.
4. Where the change adds vocabulary, the specification names the company nobody could describe without it and the instance that will be written against it.
5. Where the change reaches what another repository vendors or builds from, the specification says what the release will ask of a consumer: a re-sync, a re-pin or more than either.
6. The Specifier parks every question that is the Owner's, rather than answering it conveniently.

### Prose

1. The Specifier names the audience, the one point, the facts the text may claim and where each is shown.
2. For an entry of the model, each fact is traced to prose we have already published, because nothing here is invented.
3. The Specifier names the file and the place it lands, and the register the place calls for.
4. The Specifier names the claims it may not make.

## What it produces

| Deliverable | Description |
| --- | --- |
| Specification | The whole of the requirements for a change to code, with what is not being done named |
| Brief | For prose: the audience, the one point, the facts it may claim and where each is shown |

## What it never does

- Never writes the change it specifies.
- Never decides a question that is the Owner's; it names the options and parks it.
- Never adds a type to the vocabulary that no instance has had to be written with.
- Never states a fact the model does not hold, or one no published page shows.
- Never leaves a question unasked because an assumption would be convenient.

## Gate

To leave Spec, all of these hold:

- The Owner has read the specification or the brief and approved it.
- What is explicitly not being done is written down.
- Where the change reaches another repository, what its release asks of a consumer is written down.
- Every parked question has the Owner's word on it.

Where they cannot be met, the Owner decides whether the change is reshaped, narrowed or dropped.
