---
id: 01a1256e-487d-785c-bff3-01aed9c39917
source: Local
products:
  - CompanyGraph Core
concepts:
  - Pack
  - Type
---

# A company that runs systems describes its landscape

> A company that runs systems writes down which ones it has, what each runs on, what each offers the others, which one keeps the data of each thing it knows about and where each takes its data from, so whoever plans a replacement or answers for an outage reads it in one place.

## Description

The landscape pack, taken beside core: a system is of a kind the company names in its own words, and each kind is a specialization of one ArchiMate element, so a system goes to an architecture tool and comes back as the element it is. A system says what it runs on, who owns it and who runs it, the features it realizes and the data processor behind it; a service is what a system exposes to others, with the systems that provide it. A system names the concepts it keeps data of, one of them the master of each, and a connection is written on the system that takes the data, with the interface it goes through.

It stops at the inventory. It draws no diagram, which a consumer draws from the pages, holds no cost and no license, and says nothing yet about where a system is.

## References

| What | URL |
| --- | --- |
| The pack's documentation, with its mapping to the standard and where it departs from its sources | https://github.com/companygraph/meta-model/blob/main/packs/landscape/README.md |
| The standard for modeling an enterprise's architecture | https://pubs.opengroup.org/architecture/archimate4-doc/ |
| The file format architecture tools exchange a model in | https://www.opengroup.org/xsd/archimate/ |
| An architecture management tool's stages of an application's lifecycle | https://docs-eam.leanix.net/ |
