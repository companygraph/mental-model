---
id: 01a0ee26-c790-7cd2-9d34-008324cbeb63
source: Local
adopted: 2026-09-29
---

# A company's model belongs to no tool, and any graph database can hold it

> A company's model is Markdown files that any tool can read for as long as text can be read, and loading an instance into a graph database — Neo4j, Amazon Neptune, Ontotext GraphDB, Memgraph or another — takes no work of the company's own: no mapping to write, no code, and no page changed.

## What it makes true

The files stay the master, and a graph database holds a copy drawn from them that can be rebuilt at any commit, so a company that queries its model in one database can move it to another or drop the database without losing a fact. It holds when both kinds of graph database a company is likely to run can load an instance from what the tooling produces: a property graph queried in Cypher or GQL, and an RDF store queried in SPARQL. The copy then answers what the model says at that commit. It fails the day a fact lives only in a database, or the day a company has to write its own mapping for a type core ships.

What falls outside: running or hosting the database, and choosing one. Also outside: writing back. A change made in the database is not a change to the model, and it reaches the model only as any change does, through a person's approval.

## References

| What | URL |
| --- | --- |
| The graph database ranking the names come from | https://db-engines.com/en/ranking/graph+dbms |
