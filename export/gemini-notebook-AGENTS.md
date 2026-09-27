# CompanyGraph — the model

> CompanyGraph, described in CompanyGraph. This notebook is that model whole: {{entities}} entities across {{sources}} sources, every page as it is written in the repository it is mastered in.

The model answers questions about the company that publishes the meta-model: what it is building and toward what, the values and the strategies it works under, the product it ships and what that product lets someone do, the seats its work is done from and the agents that fill them, the processes a change goes through, the decisions it has taken and what each ruled out, and the words it means something exact by. There are no people in it. Every seat names no holder, and every profile is an agent's.

## The sources

Two of these sources carry documents about the model: this guide and the repository's README. The rest carry its {{entities}} entities.

| File | Contains | Read it when you need to |
| --- | --- | --- |
| `AGENTS.md` | this guide | Read anything else here |
| `README.md` | the repository's README | See how the model is laid out and licensed |
| `identity.md` | who the company is | Find the name and the public addresses |
| `vision.md` | the future the company works toward | Ask what the work is building toward |
| `brand.md` | what the company looks and sounds like, as meaning | Ask what carrying the name promises a reader |
| `values.md` | the {{count:Values}} values | Ask what it will and will not do |
| `strategic-objectives.md` | the objectives the vision needs made true, {{count:Strategic objectives}} entities | Ask what it is trying to make true, and how it would know |
| `strategies.md` | the strategies pursuing them, {{count:Strategies}} entities | Ask how an objective gets reached, and what the route rules out |
| `kpis.md` | the {{count:Kpis}} KPIs the company watches, each defined with what could make it lie and no value | Ask what a number counts, who answers for it and what it can hide |
| `roles.md` | the {{count:Roles}} seats its work is done from, each naming no holder | Ask what a seat is responsible for, and what it refuses |
| `profiles.md` | the {{count:Profiles}} agents that fill those seats | Ask what does the work, and in what voice it speaks |
| `processes.md` | the processes and their phases, {{count:Processes}} entities | Ask how a change gets made, phase by phase |
| `decisions.md` | the {{count:Decisions}} decisions taken, each with the alternatives it ruled out | Ask what was decided, why, and what was not chosen |
| `decision-kinds.md` | the {{count:Decision kinds}} kinds a decision is filed under | See what side of the work a decision governs |
| `decision-statuses.md` | the {{count:Decision statuses}} statuses a decision stands in | Ask whether a decision still holds |
| `domains.md` | the domains the products and the concepts name | Find which area of the company a product or a word belongs to |
| `products.md` | what the company ships | Ask what it ships, and to whom |
| `features.md` | the {{count:Features}} features its product lets someone do | Ask what someone can do with the product, and on which concepts |
| `concepts.md` | the {{count:Concepts}} words the company means something exact by | Look up what a word means here |
| `questions.md` | the {{count:Questions}} questions visitors ask, each naming the entities its answer rests on | Find where the answer to a question, asked as people ask it, lies |
| `question-kinds.md` | the {{count:Question kinds}} kinds a question is filed under | See what a visitor is asking about when they ask it |
| `sources.md` | where the pages are mastered | Check where a fact would be corrected |
| `surfaces.md` | the {{count:Surfaces}} places the model is published to | Ask what reaches a published place and what is left out |
| `meta.md` | CompanyGraph core: its conventions and its schemas, {{count:Meta}} entities | Check what a page must carry and how a reference resolves |

## How to read the model

A source is a stack of whole pages. Each one begins at a line reading `<!-- entity: … -->`, which names the file it comes from; then comes the page, unchanged. Its frontmatter fence carries the fields a validator reads. The `#` heading under the fence is the entity's name, and that name is the handle everything else uses.

**References between entities are by name, not by link.** A field or a table cell that names another entity spells it exactly as that entity's heading does. To follow a reference, take the name and find the heading.

`meta.md` holds the rules every entity obeys: which fields a page of each type must carry, how a date is written, and the rule that a reference naming something that does not exist is an error rather than a note. Read it when an answer turns on whether the model is allowed to say something, not on what it says.

## The model, live

This notebook is the model at one commit. The same model is served to agents at `https://mcp.companygraph.io/mcp`, an MCP server that reads a pinned commit of it and adds nothing, and every answer it gives names that commit. A person opening `https://mcp.companygraph.io` in a browser gets a page listing what it answers and the address to give a client. When an answer here may be out of date, that server is where the current one is; `surfaces.md` describes it as one of the places the model is published to.

## What a claim rests on

A page's `source` field names where it is mastered, and `sources.md` says what each of those places is. A fact that is wrong is corrected there and nowhere else. A public document a claim rests on is linked from its page.
