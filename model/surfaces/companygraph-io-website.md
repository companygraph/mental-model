---
source: Local
production: built
built-by: https://github.com/companygraph/companygraph.github.io
url: https://companygraph.io
---

# companygraph.io website

> The project's own site, in English and Swiss Standard German, where a visitor, a search engine or an agent meets the vocabulary and the company that publishes it, rebuilt from pinned commits of the models it draws.

## What it shows

- **Landing graph** — this company's own model, drawn as a graph from `company.json`.
- **CLI** — the one command an instance is made and kept from: what each pick of its menu does, and how the command is run from a release.
- **Team** — each process's phases as a board of the roles that own, execute, support and approve each, and the profiles that hold those roles, drawn from `company.json`.
- **Principles** — the vision and the values, drawn from `company.json`.
- **Surfaces** — every surface the model records, with how each is made and what makes it, and nothing kept beside the model, drawn from `company.json`.
- **Model** — the vocabulary, drawn: every core type with its schema, as a graph from a pinned commit of core.
- **Example** — one company, drawn: the fictional company the vocabulary's example describes, as a graph from the same commit.
- **Talks** — the introduction talk, narrated in both languages with a PDF, and the questions it ends on.
- **Billing** — how consulting would be counted if it ever were, what is free and stays so, and the ways to charge that were refused and why.
- **Privacy** — what leaves a visitor's browser and what stays in it, listed in full.
- **company.json** — this model parsed at the commit the site pins, published as a dataset.
- **Chat** — the button at the foot of every prose page and the panel it opens, answered by the chat.companygraph.io chat.
- **Structured data** — the organization, the software and the datasets each page describes to a crawler.

## Constraints

- The site collects nothing: no page sets a cookie, no page loads an analytics script, and nothing counts a visit; the one request a page makes to another address is the chat's, and only after the visitor has pressed send.
- Every page that carries a graph names the repository and the commit it was parsed from, on the page.
- A page drawn from a model is rebuilt from the artifact committed beside it, and the build fails when that artifact is not what the pinned commit parses to.
- Both languages carry the same claims: a page's German is a translation of its reviewed English, never a second text.
