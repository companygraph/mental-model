---
source: Local
production: built
built-by: https://github.com/companygraph/companygraph.github.io
url: https://companygraph.io
---

# companygraph.io website

> The project's own site, in English and Swiss German, where a visitor, a search engine or an agent meets the vocabulary and the company that publishes it, rebuilt from pinned commits of the models it draws.

## What it shows

- **Landing graph** — this company's own model, drawn as a graph from `company.json`.
- **company.json** — this model parsed at the commit the site pins, published as a dataset.
- **Model** — the vocabulary's types and the edges between them, drawn from `model.json`, which is parsed from the meta-model and not from here.
- **Example** — the invented company the vocabulary ships with, drawn from `example.json`, parsed from the meta-model and not from here.
- **Talks** — the introduction, as a deck, a PDF and audio, in both languages.
- **Billing** — what would cost money and what never does, written by hand rather than drawn from the value it restates.
- **Privacy** — what the site collects and who runs it, written by hand.
- **Structured data** — the organization, the software and the datasets each page describes to a crawler.

## Constraints

- Every page that carries a graph names the repository and the commit it was parsed from, on the page.
- A page drawn from a model is rebuilt from the artifact committed beside it, and the build fails when that artifact is not what the pinned commit parses to.
- Both languages carry the same claims: a page's German is a translation of its reviewed English, never a second text.
