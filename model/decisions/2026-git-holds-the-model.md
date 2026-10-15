---
id: 01a13dd7-fc77-7058-aa34-086986674292
source: Local
decided: 2026-10-15
kind: Architecture
status: Standing
by: Owner
upholds:
  - Run on what we publish
---

# A model is kept in git, and a store for reads stands in front of it

> We support one setup for keeping a company's model: its Markdown in git, on GitHub where the company keeps it there, as the record every check, pin and answer names, with a store for reads in front of it where a surface needs one, as the MCP server's snapshot is. Any other setup is supported once it shows it meets the requirements governance rests on.

## The question

Whether CompanyGraph supports keeping a company's model in a database. It had to be decided on October 15, 2026, when the governance research found that the checker only reads files and that what makes its verdict binding, a state with a name, a change applied whole, an author kept, a gate and the accounts that may pass it, comes from git and GitHub, so a company asking to keep its model elsewhere would be asking for every one of those.

## Alternatives

| Option | Why not |
| --- | --- |
| A database as the model's record | Every requirement git meets today, named states, change sets over a graph, differences entity by entity, would become the tooling's to build before the first check could govern anything. |
| Any store, with no setup named | A company could run the checks on a store that has no gate, and neither it nor we could tell whether its model is governed. |
| Leave it unsaid | The model would rest on git and GitHub without saying so, and a company asking would get no answer it can hold us to. |

## Why

It is the setup we run: our three models are Markdown in git, every check of the family rests on it, and the MCP server already puts a store for reads in front of it in its snapshot, so naming it supported promises nothing we have not had to do. The requirements governance rests on are now pages of CompanyGraph Core, so the bar another setup has to clear is written down rather than implied.

## Consequences

A company keeps its model in git and gets the governance the family has, and a surface that needs fast reads loads a state into a store of its own, which serves reads and is never written to. We give up a native database setup until one meets the requirements. A model kept in git on another host is supported once that host shows it meets the requirements on who may change a model and on counting every pass of the gate. Because git cannot take content out of its history, personal data stays out of every model by rule, and that rule has to hold for this call to stay right; so do the requirements, which have to keep naming what git and GitHub meet for us.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| product | CompanyGraph Core | | changed it |
