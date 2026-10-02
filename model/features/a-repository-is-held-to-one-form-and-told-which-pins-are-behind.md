---
id: 01a0fb73-abe0-792f-b857-e185354274c8
source: Local
products:
  - CompanyGraph Core
concepts:
  - Pin
  - Check
  - Release
---

# A repository is held to one form and told which pins are behind

> Every repository around a company's model, its site, its services and its server, follows one Markdown form and learns which of the releases and commits it takes have moved on, without anything moving them for it.

## Description

`form` holds every Markdown file to one fixed form; a repository may only exclude paths, and `check` and the instance workflow run it. An instance declares in `pins.json` what it takes from another repository, a release or a commit, and `pins` asks each upstream and says current, behind, unknown, unmanaged or missing. It moves nothing, because a pin that is behind is intent until someone calls it drift. A repository with no model takes the same with `adopt`: a manifest without core, the workflow, the seat hook and its own `pins.json`. The machinery is the meta-model's; the rules a company writes stay its own.
