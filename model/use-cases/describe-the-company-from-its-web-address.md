---
id: 01a1312c-107a-7444-9d52-e6f4c2161d4c
source: Local
level: user goal
scope: system
primary-actor: Owner
features:
  - An agent does the work no script can, by the skills an instance ships
includes:
  - Check a change against the schemas
---

# Describe the company from its web address

> The owner has an instance that holds what the company already publishes about itself: its identity, the sources, its products with their kinds and domains, its vision and values where it states them, the questions its site answers and a thin profile for each person the owner kept, every fact traced to the page it was read from.

## Stakeholders and interests

| Stakeholder | Interest |
| --- | --- |
| Owner | Every row and every name decided by them, one question at a time with a proposal |
| Person on a team page | Struck by name, and then mentioned nowhere |
| Company described | A sentence carried verbatim only where its terms or a consent allow it |

## Preconditions

- An instance the command wrote, or one with content to reconcile against.

## Trigger

The owner gives the agent the company's web address.

## Main success scenario

| Step | Actor | Action |
| --- | --- | --- |
| 1 | Owner | Says whether to create or update, and gives the address |
| 2 | Agent | Reads the robots file first, then the front page and the imprint, and confirms the company's name with the owner before anything else |
| 3 | Agent | Reads the pages a person would read to learn what the company is, and its GitHub organization, and writes every page read to a ledger with its address and the date |
| 4 | Agent | Takes out only what a schema has a place for, and proposes it type by type, one question per turn with a proposal |
| 5 | Owner | Keeps, strikes or renames each row, and each person on a team page by name |
| 6 | Agent | Records the terms and consents for every source the kept rows name |
| 7 | Agent | Writes the sources first, then the identity, the domains, kinds, products and features, the vision and values, the question kinds and questions, and the kept profiles, each page with a fresh id and every tagline shown as a draft |
| 8 | Owner | Holds the pages to their schemas, as Check a change against the schemas says, and commits |

## Extensions

| Step | Condition | Handling |
| --- | --- | --- |
| 2a | The robots file disallows a path | No later step reads it, and the ledger says so |
| 2b | On an update, the name is a different company's | The agent stops, asks whether to create a new instance instead, and on no writes nothing |
| 3a | The ledger's folder is not ignored by git | The agent asks and adds it to the ignore file before the ledger is written, since the ledger names every person on a team page, the ones the owner will strike included |
| 4a | A page states a number that moves, a revenue, a headcount, a funding round, a founding year as an age | It is not extracted and not noted anywhere |
| 6a | The company's own consent is needed and not given | The run ends with nothing written except the report and the proposed line for the agent file |
| 6b | A person's consent is not given | That person's rows are dropped and the run goes on |

## Minimal guarantees

- A person struck is mentioned nowhere in the model.
- Nothing is committed by the run; the commit is the owner's.

## Success guarantees

- Every fact in the instance names the source it was read from, and every tagline is marked as a draft for the owner.

## References

| What | URL |
| --- | --- |
| The company procedure | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-company/SKILL.md |
| The consent procedure | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-consent/SKILL.md |
