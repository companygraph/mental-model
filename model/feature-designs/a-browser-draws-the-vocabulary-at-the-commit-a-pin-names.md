---
id: 01a10042-637e-7b18-8ccc-106a7ca249f4
source: Local
refines: The vocabulary on the web
contexts:
  - Publishing
  - Resolution
decisions:
  - A model is written in one language
---

# A browser draws the vocabulary at the commit a pin names

> The model page and the example page draw files built once from one pinned commit of the meta-model, so what a reader walks in a browser and what an agent fetches are the same model at the same commit.

## Operational principle

Someone moves the site's meta-model pin; the build reads core, every pack and the example at that commit, the graph is drawn, and two artifacts are written with the commit inside them; the model page and the example page fetch them, draw them and name that commit beside the figure.

## Scenarios

### SC-P1: The vocabulary drawn at its pin

Given the meta-model pin at a commit, when the artifacts are built and a reader opens the model page, then the stage page draws a folder for core and one for each pack, a square for each schema in them, a dashed line for each field that references another type, and the commit it was drawn at beside the figure.

### SC-P2: A pack shipped upstream is drawn at the next pin

Given a pack released in the meta-model after the site's pin, when the pin is moved to a commit that holds it and the artifacts are built, then the model page draws the pack's folder and schemas with no change to the site's code.

### SC-P3: An artifact behind its pin draws nothing new

Given a pin moved without the artifacts being built again, when the derived regions are rendered or the site's checks run, then the render refuses, names the artifact and the pin's commit, and says to run the build.

### SC-P4: A commit that does not resolve is not published

Given a commit where the example names something that resolves to nothing, when the artifacts are built, then the build stops and says where the name was written and what it searched, and the committed artifacts stay as they were.

### SC-P5: An agent fetches the vocabulary as a file

Given the model page, when an agent reads its JSON-LD, then it finds the vocabulary as a term set whose encoding is `model.json`, each term linked to its schema file at the pinned commit, and the example page's dataset names `example.json` as its download.

### SC-P6: A German reader reads the model in its own language

Given a reader on the model page, when they switch the page to German, then the page around the figure and the stage's own labels read in Swiss Standard German, and the schemas it draws stay in the one language the model is written in, as the page says beside them.

## Uses

| Type | Entity | Context |
| --- | --- | --- |
| concept-design | Pin | Publishing |
| concept-design | Artifact | Publishing |
| concept-design | Stage page | Publishing |
| concept-design | Derived region | Publishing |
| domain-event | Artifact built | Publishing |
| domain-event | Graph drawn | Resolution |
| domain-event | Name found unresolvable | Resolution |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/companygraph.github.io/blob/main/build/build.mjs |
| Implementation | https://github.com/companygraph/companygraph.github.io/blob/main/stage.js |
| Implementation | https://github.com/companygraph/companygraph.github.io/blob/main/build/jsonld.mjs |
| The model page | https://companygraph.io/model/ |
