---
id: 01a0c202-d668-77f0-8e1f-222f104c28ed
source: Local
owner: Owner
executed-by:
  - Owner
  - Partner
gate-approvers:
  - Owner
  - Partner
escalation-authority: Owner
gate-to: Spec
---

# Shape

> Decide what kind of change this is, how far it reaches, and how much of it gets written down.

## What it takes

A request in whatever words it arrived in, and the part of the model, the vocabulary or the repository it will have to agree with, read rather than remembered.

## Activities

1. The Owner states the request as one sentence.
2. The Owner classifies it: a question whose output is an answer, a bounded change to something already here to read or a change to how things fit together.
3. The Owner names the track it runs on.
4. The Owner names how far it reaches: what another repository vendors or builds from, and what surface is rebuilt from a commit of it.
5. The Owner says which phases write a document and which are satisfied in conversation.
6. The Owner names what is explicitly not being changed.

## What it produces

| Deliverable | Description |
| --- | --- |
| Classification | Which of the three kinds of change this is, and why |
| Track | Which track the work runs on, named as the process spells it |
| Reach | What the change makes stale: what vendors it, what builds from it, and what is rebuilt when it lands |
| Document plan | Which phases produce a file and which are answered in conversation |

## What it never does

- Never classifies by how familiar the work feels rather than by what exists to read.
- Never lets a classification skip a gate; only the document scales, never the approval.
- Never begins the work it is classifying.

## Gate

To leave Shape, all of these hold:

- The request is stated as one sentence.
- The track is named.
- What the change makes stale is named, or named as nothing.
- The classification is stated, and the phases that will write a document are named.

## If not met

| Outcome | Leads to |
| --- | --- |
| reshaped | Shape |
| dropped | |
