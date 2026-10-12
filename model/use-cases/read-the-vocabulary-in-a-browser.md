---
id: 01a1312c-6c2c-7e41-95ac-db5c3591d128
source: Local
level: user goal
scope: system
primary-actor: Visitor
features:
  - The vocabulary on the web
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

## References

| What | URL |
| --- | --- |
| The model page | https://companygraph.io/model/ |
| The site's build | https://github.com/companygraph/companygraph.github.io/blob/main/build/build.mjs |
