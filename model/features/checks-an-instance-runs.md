---
source: Local
products:
  - CompanyGraph Core
---

# Checks an instance runs

> A company finds out before a change lands whether its pages still hold to the schemas it adopted.

## Description

The mechanical half of validation: a checker shipped in every release, which an instance's workflow calls at the release its manifest names. It reads the schemas from the core the instance vendored, never from its own, so taking a newer release never holds an instance to rules it has not adopted, and a checker that is not the named release refuses to run. It stops at what a script can read: whether a page keeps its schema's writing rules is the agent pass, and every run says so.
