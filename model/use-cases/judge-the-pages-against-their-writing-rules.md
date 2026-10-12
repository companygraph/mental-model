---
id: 01a1312c-1fcc-7558-be2f-4183eee8e01d
source: Local
level: user goal
scope: system
primary-actor: Owner
features:
  - A decision model asks each page its schema's writing rules
  - An agent does the work no script can, by the skills an instance ships
---

# Judge the pages against their writing rules

> The owner knows which pages most likely break a writing rule before anyone reads them, having decided first exactly what left their hands to find out, and has a reading of each flag against its page.

## Stakeholders and interests

| Stakeholder | Interest |
| --- | --- |
| Owner | What leaves the machine decided by them, every run, over exactly the files shown |
| Writer | A finding with a fix proposed concretely enough to apply as written |
| Agent | A report that is advisory, so its reading never stands in for the pass that reads every page |

## Preconditions

- The folder the report is written to is ignored by git, since the report quotes the pages.
- The owner's key for the service is in their own environment and nowhere in the conversation.

## Trigger

The owner asks for the judge.

## Main success scenario

| Step | Actor | Action |
| --- | --- | --- |
| 1 | Agent | Runs the judge without the key, so nothing can be sent, and takes the counts, the service, host and model, the forecast of tokens, requests and cost, the file list and the digest |
| 2 | Agent | Asks the owner whether to send, in plain words: these pages leave this machine whole, to an outside service, and a yes covers exactly the files under this digest and nothing changed after it |
| 3 | Owner | Says yes |
| 4 | Agent | Runs the judge with the digest as consent and the key from the owner's environment, and writes the report beside the instance |
| 5 | Agent | Reads the flags the owner already decided, then each remaining flag against its page and the rule's own words, and groups the ones that stand by cause |
| 6 | Agent | Writes the reading beside the report: findings with a proposed fix, false flags, known flags, rows proposed for known, and what was not checked |
| 7 | Owner | Decides the fixes and the rows one at a time, and the agent writes the approved rows to the known file and checks them |

## Extensions

| Step | Condition | Handling |
| --- | --- | --- |
| 1a | The report's folder is not ignored by git | The agent says the report would quote the pages in a folder git could commit, and stops; nothing is sent and nothing written |
| 3a | The owner says no | Nothing is sent, and the use case ends |
| 4a | What would be sent has changed since the digest | The run refuses, and the owner is asked again over the new file list, counts and digest |
| 4b | The key is not set | The agent says so and stops |
| 5a | A flag has a known row whose hash differs | The row has lapsed, since the page or the rule changed after the owner decided, and the flag is read like any other |

## Minimal guarantees

- Nothing leaves the machine without the owner's yes to exactly what was shown, and a yes given for another digest, an earlier run or another instance counts for nothing.
- No entry is changed by the judge; a fix is proposed and made on the owner's word.

## Success guarantees

- The owner holds the report and a reading of every flag, with the findings grouped by cause and a fix proposed for each.

## References

| What | URL |
| --- | --- |
| The judge procedure | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-judge/SKILL.md |
