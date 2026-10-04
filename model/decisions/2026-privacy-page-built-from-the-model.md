---
id: 01a107f3-304f-7047-8b13-1ec5c0097c23
source: Local
decided: 2026-10-04
kind: Data protection
status: Standing
by: Owner
upholds:
  - Run on what we publish
---

# companygraph.io's privacy page is built from the model

> The privacy page on companygraph.io is built from this model's data processors, processing activities and stored items, at the pinned commit the site draws, so what the page names is what the model holds and a correction is made once, in the model.

## The question

Core 0.60.0 gave the model types for what a privacy page discloses, and on the day they were written the page had drifted from what the site and the chat do: it named neither Google Cloud, which runs the chat and keeps its questions, nor the chat-facts key, and still said that everything stored was listed. Either the page is corrected by hand and kept in step by hand, or it is built from the model.

## Alternatives

| Option | Why not |
| --- | --- |
| Correct the page by hand now and keep it in step by hand | That is how it drifted: the facts were written in the page and in the code, and nothing compared them. The model would be a third copy to keep in step. |
| Leave the page as it is and keep the model as the record | A visitor reads the page and not the model, so the page would go on telling them less than the company knows. |

## Why

The model is the master: a page built from it cannot name less than the model holds, and a fact corrected in the model reaches the page on the next build. The site already builds its model pages from a pinned commit of this model, so the privacy page joins a build that exists rather than starting one.

## Consequences

companygraph.github.io gains a build for the privacy page from the processors, activities and stored items at its pinned commit; the prose around them, who runs the site, what is not used at all and the model a company writes for itself, stays written by hand. Until that build exists the page stays out of step with the model, without Google Cloud and the chat-facts key. The privacy pages of the other two sites are their own instances' calls. The call stays right for as long as every key a surface sets and every party that receives a visitor's data has a page in the model; a key added to the code without one is the next drift, which a check of the site's keys against the model would catch.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| surface | companygraph.io website | | its Privacy page is built from the model |

## References

| What | URL |
| --- | --- |
| The privacy page | https://companygraph.io/privacy/ |
| The rule that the model is the master, R17 | https://github.com/companygraph/meta-model/blob/main/core/CONVENTIONS.md |
