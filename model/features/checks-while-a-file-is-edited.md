---
source: Local
products:
  - CompanyGraph Core
concepts:
  - Check
  - Rule
  - Schema
  - Reference
---

# Checks while a file is edited

> Someone writing a page sees what its schema requires, and what they broke, while they type rather than when the change is pushed.

## Description

A plugin for Obsidian over any instance. It runs the checks a release ships as a file is edited and marks what fails where it is written, completes a reference or a section from what the schemas declare, and renames an entity everywhere its name is used. It bundles the checker of the release it was built with and refuses a vendored core newer than that, rather than check a vault against rules it does not know. It stops at the editor: the gate a change has to pass is still the checks an instance runs.
