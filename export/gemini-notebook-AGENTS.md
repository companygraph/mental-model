# CompanyGraph — the model

> CompanyGraph, described in CompanyGraph. This notebook is that model whole: {{entities}} entities across {{sources}} sources, every page as it is written in the repository it is mastered in.

## The sources

Two of these sources carry documents about the model: this guide, `AGENTS.md`, and the repository's `README.md`, which says how the model is laid out and licensed. The rest carry its {{entities}} entities, each source named for what it holds, most of them for one type. An entity of which there is only one has a source of its own, as `identity.md` and `vision.md` do. `meta.md` holds CompanyGraph core, its conventions and its schemas, and `sources.md` holds the places the pages are mastered in.

## How to read the model

A source is a stack of whole pages. Each one begins at a line reading `<!-- entity: … -->`, which names the file it comes from; then comes the page, unchanged. Its frontmatter fence carries the fields a validator reads. The `#` heading under the fence is the entity's name, and that name is the handle everything else uses.

**References between entities are by name, not by link.** A field or a table cell that names another entity spells it exactly as that entity's heading does. To follow a reference, take the name and find the heading.

`meta.md` holds the rules every entity obeys: which fields a page of each type must carry, how a date is written, and the rule that a reference naming something that does not exist is an error rather than a note. Read it when an answer turns on whether the model is allowed to say something, not on what it says.

## The model, live

This notebook is the model at one commit. The same model is served to agents at `https://mcp.companygraph.io/mcp`, an MCP server that reads a pinned commit of it and adds nothing, and every answer it gives names that commit. A person opening that address in a browser gets a page listing what it answers. When an answer here may be out of date, that server is where the current one is; `surfaces.md` describes it as one of the places the model is published to.

## What a claim rests on

A page's `source` field names where it is mastered, and `sources.md` says what each of those places is. A fact that is wrong is corrected there and nowhere else. A public document a claim rests on is linked from its page.
