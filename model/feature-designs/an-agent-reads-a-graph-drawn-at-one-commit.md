---
id: 01a10031-78b1-7a27-aba6-d813a9b2781f
source: Local
refines: An agent reads the model
contexts:
  - Resolution
decisions:
  - The server only reads, and answers at one named commit
---

# An agent reads a graph drawn at one commit

> The server answers from a graph drawn once, at the commit its deployment names, so every edge it reports was resolved before the first question.

## Operational principle

The deployment draws the graph at its pinned commit when it is built; the server answers every question from that graph and names the commit in each answer.

## Scenarios

### SC-A1: An entity with its edges

Given a graph drawn at a commit, when an agent asks for an entity, then the answer gives its references resolved to ids, each with the field or column that drew it, and the commit.

### SC-A2: A model that does not resolve is not served

Given a commit where a page names nothing, when the deployment is built, then no graph is drawn and nothing is served from that commit.

### SC-A3: A renamed entity keeps its edges

Given an edge to an entity, when that entity's page is renamed and the graph drawn again, then the edge still joins the same id.

## Uses

| Type | Entity | Context |
| --- | --- | --- |
| concept-design | Graph | Resolution |
| concept-design | Edge | Resolution |
| domain-event | Graph drawn | Resolution |
