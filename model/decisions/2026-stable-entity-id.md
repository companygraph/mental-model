---
id: 01a0f0ed-5db8-7589-9ab1-df069dbad08c
source: Local
decided: 2026-09-30
kind: Vocabulary
status: Standing
by: Owner
serves:
  - A company's model belongs to no tool, and any graph database can hold it
---

# Every entity carries an id that outlives its name

> Every entity carries an id in its frontmatter, set once and never changed or reused, in the
> format the instance's identifier file declares, and every tool returns that id, so a link
> from outside the model survives a rename.

## The question

What an outside system holds on to when it links to an entity: a task to the feature it delivers, a commit to the decision it carries out, a node in a graph to the page it was loaded from. The only id the model offered was the folder and the slug of the H1, which changes the day the entity is renamed. It had to be decided in September 2026, when an adopter asked it in meta-model #194 and the chat answered that the model does not say.

## Alternatives

| Option | Why not |
| --- | --- |
| Keep the path as the id and list former names under `formerly` | An old name that still resolves stops R4 from catching a stale reference inside the model, and a deleted entity would never be gone. |
| A number per type from a counter in the instance | Two branches take the same number, every new entity edits one file, and a counter worked out from the highest number reuses the id of a deleted entity. |
| A prefix naming the type before a random part | The type is part of the id, and the id is wrong the day an entity moves from one type to another. |
| One format in core, with no way for an instance to declare another | An instance with a scheme of its own, an employee number or a record key, would have to keep a second id beside ours. |

## Why

An id that means nothing can outlive everything that does: the name, the type, the language. A UUID version 7 needs nobody to hand it out, so every worktree and every agent can make an entity without knowing about the others, and it sorts by when the entity was made. It works like a row in a database: a deleted row is gone, and its id is never used again.

## Consequences

Every schema declares `id`, the new core type `identifier` is a file every instance carries, and R18 states what an id promises. The MCP server and the plugin take an id or a current path and always return the id. Page addresses stay readable, while the JSON-LD `@id` becomes `/id/<uuid>` and redirects to the page. Existing entities get ids stamped with their first commit time. What it gave up is a reader following an old name: after a rename, the old path is not found.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| concept | Entity | | changed it |
| feature | An agent reads the model | | changed it |
| feature | The vocabulary on the web | | changed it |
| feature | Checks an instance runs | | changed it |

## References

| What | URL |
| --- | --- |
| The issue | https://github.com/companygraph/meta-model/issues/194 |
| The specification | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-09-30-an-entity-keeps-its-id-design.md |
