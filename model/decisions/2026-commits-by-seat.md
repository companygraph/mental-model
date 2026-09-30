---
id: 01a0e828-3018-7900-a053-21ddaf9d67e2
source: Local
decided: 2026-09-28
kind: Architecture
status: Standing
by: Owner
upholds:
  - Run on what we publish
---

# An agent's commit is authored by the seat it held

> A commit an agent makes in our repositories is authored by the seat it held, at our domain, as `Implementer <implementer@companygraph.io>`, and names the process, phase and track it was made in; the owner's own commits stay the owner's, and a check refuses a seat the named phase does not list.

## The question

Whose name an agent's commit carries. Our processes name the seats that execute each phase and agents do most of the Delivery work, yet every commit carried the owner's name. It had to be decided before the hook and the report were specified, on September 28, 2026, because the tooling writes and checks whatever the call says.

## Alternatives

| Option | Why not |
| --- | --- |
| The owner's name on every commit, as before | The history could not say which seat did the work, or in which process. |
| The owner's name as the author, and the seat only in a trailer | GitHub and `git shortlog` group by author, so every report by seat would need tooling to read a trailer, and the owner's commits could not be told from an agent's at a glance. |
| An email field on each seat | A second copy of what the model already derives from the role's name and the identity's `url`, free to drift from it. |
| An `owner@` address for the owner's commits | The owner's name already means the owner, and a report tells people from agents by exactly that difference. |
| A Claude Code hook refusing a commit made without `--author` | It would guard one agent and be a rule no other agent sees, where the `commit-msg` hook is the one every agent meets. |

## Why

We publish a vocabulary in which a process names the seats that execute each phase, and a company running on it should be able to check its own history against those seats. Authoring by seat puts that vocabulary on each commit, checked against the phase that lists the seat, so a report by seat is read from git rather than reconstructed, and with each seat's address verified on the owner's GitHub account every commit still links to the owner.

## Consequences

Every seat that commits needs an address on our domain, a mail alias onto the owner's mailbox verified on the owner's GitHub account. The Owner, the Controller, the Reviewer, the Answerer, the Visitor, the Contributor and the Requestor get none, because they never commit as a seat: the owner commits under the owner's own name, the Controller writes nothing, the Reviewer returns findings, the Answerer answers at runtime, and a Visitor, a Contributor or a Requestor commits under their own name. companygraph.io receives mail, so the hook is on in our repositories, in every clone that has run `conventions-sync`. The owner's own commits are authored as robert@blust.ch, the address the owner's profile carries, so the report counts them as the owner's. Commits made before the rule keep the author they have, because rewriting published history would force-push every repository. The call stays right for as long as agents do the work under seats our processes name, and the processes stay what the check reads.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| role | Specifier | | changed it |
| role | Planner | | changed it |
| role | Implementer | | changed it |
| role | Writer | | changed it |
| role | Translator | | changed it |
| role | Narrator | | changed it |

## References

| What | URL |
| --- | --- |
| Specification | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-09-28-a-commit-names-its-seat-design.md |
| Pull request of the specification | https://github.com/companygraph/meta-model/pull/179 |
