---
id: 01a1312c-6c2c-7e41-95ac-db5c3591d128
source: Local
level: user goal
scope: system
primary-actor: Visitor
features:
  - The vocabulary on the web
realization: Main scenario released
---

# Read the vocabulary in a browser

> A visitor reads the vocabulary, and sees it describe a company, in a browser and without cloning a repository, drawn at the same commit an agent fetches.

## Stakeholders and interests

| Stakeholder | Interest |
| --- | --- |
| Visitor | The vocabulary at the commit the page names, in the language they read |
| Owner | A build that refuses a commit that does not resolve, and leaves the published pages as they were |

## Trigger

The visitor opens the model page of the site.

## Main success scenario

| Step | Actor | Action |
| --- | --- | --- |
| 1 | Visitor | Opens the model page |
| 2 | System | Draws a folder for core and one for each pack, a square for each schema in them, a dashed line for each field that references another type, and the commit it was drawn at beside the figure |
| 3 | Visitor | Opens the example page and sees a company described in the vocabulary |
| 4 | Agent | Reads the model page's JSON-LD and finds the vocabulary as a term set, each term linked to its schema file at the pinned commit |

## Extensions

| Step | Condition | Handling |
| --- | --- | --- |
| 2a | The visitor switches the page to German | The page around the figure and the stage's own labels read in Swiss Standard German, and the schemas it draws stay in the one language the model is written in, as the page says beside them |
| 2b | The build ran on a commit where the example names something that resolves to nothing | The build stops, says where the name was written and what it searched, and the published pages stay as they were |

## Minimal guarantees

- What the page shows and what an agent fetches are the same model at the same commit.
- The published pages stay as they were when a build stops.

## Success guarantees

- The visitor has read the vocabulary at a named commit without cloning anything.

## Realization

At the deployed commit the site's `build/build.mjs` reads the schemas of core and the packs at the pinned meta-model commit and writes `model.json`, and `stage.js` draws a folder per pack, a square per schema, a dashed line per reference field and the commit beside the figure (steps 1 and 2); the example page is drawn from `example.json` (3); `build/jsonld.mjs` writes the model page's term set with each term's `url` at `blob/<commit>/` of its schema file (4). The German switch (2a) is checked by the suite; the statement that the schemas stay English is on the page and not asserted. The build stops with the parser's R4 message, naming the value, where it was written and the type searched, and writes nothing for that target (2b). The site's `verify` suite and `pages:check` check the model page's figure, its provenance and the term set separately; none walks from the model page to the example page to the term set, and the pin of the parser is v0.94.0 where v0.95.0 is the latest tag.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `build/build.mjs` | satisfies | https://github.com/companygraph/companygraph.github.io/blob/3f8e4a25f599cc0e3c77cce8cce17e585d7a6b0e/build/build.mjs |
| `build/jsonld.mjs` | satisfies | https://github.com/companygraph/companygraph.github.io/blob/3f8e4a25f599cc0e3c77cce8cce17e585d7a6b0e/build/jsonld.mjs |
| `verify/check.mjs` | satisfies | https://github.com/companygraph/companygraph.github.io/blob/3f8e4a25f599cc0e3c77cce8cce17e585d7a6b0e/verify/check.mjs |
| `build/renderers.test.mjs` | satisfies | https://github.com/companygraph/companygraph.github.io/blob/3f8e4a25f599cc0e3c77cce8cce17e585d7a6b0e/build/renderers.test.mjs |

## References

| What | URL |
| --- | --- |
| The model page | https://companygraph.io/model/ |
| The site's build | https://github.com/companygraph/companygraph.github.io/blob/main/build/build.mjs |
