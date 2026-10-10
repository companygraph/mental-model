---
id: 01a1256e-29ae-7c5e-8e99-e6f70d2beda3
source: Local
products:
  - CompanyGraph Core
concepts:
  - Pack
  - Type
---

# A company that builds software describes how it designs it

> A company that builds software writes down its bounded contexts, the terms each one's language holds, the aggregates and events inside them and how a feature is built across them, in the words of domain-driven design, as a refinement of the concepts and features it already describes.

## Description

The software pack, taken beside core: a bounded context with how much it matters to build well, the terms of its language as entities and value objects, the aggregates that keep them consistent with the commands they handle, the domain events other contexts consume, and a feature design saying how one feature is built across the contexts it touches. A term refines a core concept and a feature design a core feature, so a reader goes from what the company means by a word to how its software keeps it.

It stops at the design. It generates no code and reads none, so nothing holds the code to the pages. An architecture decision is a core decision the pack's pages name, not a type of its own.

## References

| What | URL |
| --- | --- |
| The pack's documentation, with where it departs from its sources | https://github.com/companygraph/meta-model/blob/main/packs/software/README.md |
| The reference of domain-driven design's patterns, by the author who named them | https://www.domainlanguage.com/wp-content/uploads/2016/05/DDD_Reference_2015-03.pdf |
| A short introduction to domain-driven design | https://www.oreilly.com/library/view/domain-driven-design-distilled/9780134434964/ |
| A canvas for describing one bounded context | https://github.com/ddd-crew/bounded-context-canvas |
| A canvas for designing one aggregate | https://github.com/ddd-crew/aggregate-design-canvas |
| The patterns two bounded contexts relate by | https://github.com/ddd-crew/context-mapping |
| A book on concepts as the units of software design | https://essenceofsoftware.com/ |
| The reference of a language for writing behavior as examples | https://cucumber.io/docs/gherkin/reference/ |
