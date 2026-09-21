---
source: Local
products:
  - CompanyGraph Core
concepts:
  - Instance
  - Entity
  - Reference
  - Pin
---

# An agent reads the model

> An agent asks a company's model which types it declares, what one entity says and what evidence a claim rests on, and gets the answer the model gives at one commit.

## Description

A server speaking the Model Context Protocol over any instance, parsed from one pinned commit: it lists the types a company declares, returns an entity with its references resolved, searches the model and finds the evidence a claim rests on. It only reads. It writes nothing back, adds nothing of its own, and answers at the commit its deployment names, so two agents asking one question get one answer. It stops at the server: where it runs, and over which instance, is each deployment's own.
