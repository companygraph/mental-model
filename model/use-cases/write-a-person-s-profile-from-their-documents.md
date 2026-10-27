---
id: 01a1312c-0139-734c-9a84-5c9f52e02941
source: Local
level: user goal
scope: system
primary-actor: Owner
features:
  - A profile is written from a person's documents
  - An agent does the work no script can, by the skills an instance ships
includes:
  - Check a change against the schemas
realization: Main scenario released
---

# Write a person's profile from their documents

> The owner has a profile for a person in the model, its experiences and the skills they show at the levels the documents earn, written from the person's own CVs, diplomas, certificates and reference letters, with every level and every sentence in the person's voice theirs to decide.

## Stakeholders and interests

| Stakeholder | Interest |
| --- | --- |
| Owner | Every level, seat and sentence in the person's voice decided by them, not by the agent |
| Person described | Nothing from documents no consent covers, and no fact no schema holds |
| Agent | A schema as the contract, so no fact is written that has no place |

## Preconditions

- A folder holds the person's documents.
- The instance ships the profile and consent procedures.

## Trigger

The owner asks the agent to write a profile from a folder, or to extend one.

## Main success scenario

| Step | Actor | Action |
| --- | --- | --- |
| 1 | Owner | Points the agent at the folder and says whether to create a profile or update a chosen one |
| 2 | Agent | Asks for the person's consent where the documents are not the owner's own, and records the terms the content is used under |
| 3 | Agent | Reads every document and writes the profile and its experiences against their schemas, naming each skill the model already holds by its H1 |
| 4 | Agent | Shows each level with the rows behind it, and each sentence in the person's voice, as a proposal |
| 5 | Owner | Decides each, and the agent writes what was decided |
| 6 | Owner | Holds the pages to their schemas, as Check a change against the schemas says |

## Extensions

| Step | Condition | Handling |
| --- | --- | --- |
| 2a | The person's consent is not given | The run writes nothing |
| 2b | The owner models themselves | No consent is asked, and the report says so in one line |
| 3a | A document states a fact no schema holds, a birth date | The fact is written nowhere, and the report names it by its kind and not by its value |
| 3b | On an update, the documents describe a different person | The agent asks whether to create a new profile instead, and on no writes nothing |
| 3c | An Evidence row's experience does not list that row's skill | The agent stops and asks whether the skill belongs on the experience or the row names another period |
| 4a | A new document would change a claimed level | The level is proposed with the rows behind it and left as it is until the owner decides |

## Minimal guarantees

- No level moves on new evidence by itself.
- Nothing from a person's documents is written without that person's consent, and no fact no schema holds is written anywhere.

## Success guarantees

- The profile and its experiences pass their schemas, each skill named by its H1, and each level rests on a period that shows it.

## Realization

meta-model v0.95.0 ships `companygraph-profile` and `companygraph-consent`, which `init` writes and hashes. The profile skill asks create or update and the folder (steps 1), reads every document and takes out only what a schema holds, leaving a birth date or a salary unwritten and out of any note (3a), asks for the person's consent where the documents are not the owner's own and writes nothing without it (2 and 2a, step 6 of the skill), takes none from the owner modeling themselves with one line in the report (2b), stops on update when the documents describe another person (3b), shows each level with the rows behind it and each sentence in the person's voice, and decides nothing until the owner does (4, 4a and 5), stops and asks when an Evidence row's experience does not list the row's skill (3c), and ends with check and the validate procedure (6). The tests that mention it check only that init writes the skill. Nothing runs the procedure or observes the success guarantee.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `agents/claude/skills/companygraph-profile/SKILL.md` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/agents/claude/skills/companygraph-profile/SKILL.md |
| `agents/claude/skills/companygraph-consent/SKILL.md` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/agents/claude/skills/companygraph-consent/SKILL.md |

## References

| What | URL |
| --- | --- |
| The profile procedure | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-profile/SKILL.md |
| The consent procedure | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-consent/SKILL.md |
