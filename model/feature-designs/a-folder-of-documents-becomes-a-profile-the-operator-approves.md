---
id: 01a10042-62e7-79af-ae15-8113836ac9b6
source: Local
refines: A profile is written from a person's documents
contexts:
  - Procedures
decisions:
  - Agents write the model, and a person approves every change to it
---

# A folder of documents becomes a profile the operator approves

> An agent reads every document in a person's folder and writes the profile and its experiences against their schemas, reusing what the model holds, while every level, seat and sentence in the person's voice stays the operator's to decide.

## Operational principle

Handed a folder of a person's CVs and certificates, the agent lists every file before reading any, reads each, proposes only the skills, levels, kinds and seats the model lacks, writes the experiences and then the profile, runs the checks and the agent pass, and leaves the change for the operator to approve and commit.

## Scenarios

### SC-W1: A skill the model holds is reused

Given a model holding a skill, when a document shows the person using it, then the experience names that skill by its H1 and no second skill is proposed.

### SC-W2: A fact no schema holds is dropped

Given a CV that states a birth date, when the folder is read, then the date is written nowhere, and the report names a fact left out by its kind and not by its value.

### SC-W3: Evidence must name a period that shows the skill

Given an Evidence row whose Experience does not list that row's skill, when the profile is written, then the agent stops and asks whether the skill belongs on the experience or the row names another period.

### SC-W4: A different person stops an Update

Given an Update of a chosen profile, when the documents describe a different person, then the agent asks whether to create a new profile instead, and on no writes nothing.

### SC-W5: Consent from someone else's documents

Given documents of a person who is not the instance's owner, when that person's consent is not given, then the run writes nothing, and when the owner models themselves, no consent is asked and the report says so in one line.

### SC-W6: New evidence never moves a level by itself

Given an Update where a new document would change a claimed level, when the reconciliation is shown, then the level is proposed to the operator with the rows behind it and left as it is until the operator decides.

## Uses

| Type | Entity | Context |
| --- | --- | --- |
| concept-design | Procedure run | Procedures |
| concept-design | Reconciliation | Procedures |
| concept-design | Agent pass | Procedures |
| domain-event | Change left for approval | Procedures |
| domain-event | Consent declined | Procedures |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-profile/SKILL.md |
| Implementation | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-consent/SKILL.md |
