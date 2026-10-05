---
id: 01a10042-593c-7fc9-b96e-fd14be5decb8
source: Local
classification: supporting
realizes:
  - Core
decisions:
  - A model is written in one language
  - Every entity carries an id that outlives its name
---

# Publishing

> Draws a site's pages from a model at the commit its pin names: the files an agent fetches, the stage that draws them, the graph a crawler reads, the share cards and the sitemap. Answering a visitor's question about the model is left to Answering.

## Responsibilities

- Build each artifact from the one commit its pin names, and refuse a local checkout that sits at another
- Hold every committed artifact to what its pin parses to, so a model change reaches the site only through a moved pin
- Render every derived region from the artifacts, and refuse an artifact whose commit is not its pin's
- Describe each stage page to a machine as the dataset or term set it draws, with the artifact as its download
- Give every entity of the company with a stable id an address that sends a reader on to its place on the stage
- Keep each share card to the page it was rendered from, and say when a card has fallen behind
- Date each sitemap entry by its page's last commit
- Report how far each pin is behind what it points at, and never move one

## Relationships

| Context | Pattern |
| --- | --- |
| Resolution | conformist |
| Vendoring | conformist |

## Consumes

| Type | Entity | Context | Reaction |
| --- | --- | --- | --- |
| domain-event | Graph drawn | Resolution | Build the artifacts: the drawn graph is written, with its commit, as the artifact its pin names |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/companygraph.github.io/blob/main/build/build.mjs |
| Implementation | https://github.com/companygraph/companygraph.github.io/blob/main/build/pages.mjs |
| Working conventions | https://github.com/companygraph/companygraph.github.io/blob/main/AGENTS.md |
