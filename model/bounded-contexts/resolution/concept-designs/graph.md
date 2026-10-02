---
id: 01a0faae-d24d-74b8-ac6d-73dc448cbe5d
source: Local
kind: entity
refines: Instance
---

# Graph

> An instance read at one commit: every entity its pages describe and every edge their references draw, and nothing a page only mentions.

## Attributes

| Attribute | Type | Description |
| --- | --- | --- |
| Commit | commit hash | The commit the graph was read at, which names it |
| Core version | version | The core release the instance vendors |
| Entities | list of entities | Every page that describes an entity, each with its id, type and canonical name |

## Relations

| Concept | Cardinality | As |
| --- | --- | --- |
| Edge | many | |
