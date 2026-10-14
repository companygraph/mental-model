---
id: 01a13b44-b87e-7d94-87ed-b6dee6d92385
source: Local
kind: preventive
mode: automated
enforces:
  - The Owner's word merges
---

# Only the Owner's account changes main

> The default branch of each of our repositories takes a push or a merge from the Owner's account alone, so anyone else with write access can open a branch and a pull request but cannot merge it.

## How it is carried out

GitHub's branch protection on each repository's default branch, on every push and every merge into it: it restricts who may push to the Owner's account, so a member of the organization, who holds write access through its base permission, can push a branch and open a pull request and is refused the merge. The protection holds nothing else; the pull request and the checks are what Main takes a change only through a green, current pull request holds. It is set as branch protection and not as a rule of the ruleset, because a ruleset lets only its bypass actors past such a rule, which would turn every merge the Owner makes into a bypass that Merges Past Their Checks counts. An agent working under the Owner's account passes it, so what holds an agent to the Owner's word is An agent's permissions refuse a merge it was not given.

## Applies to

| Type | Entity | Owner |
| --- | --- | --- |
| phase | Integrate | Delivery |
| phase | Integrate | Contribution |

## References

| What | URL |
| --- | --- |
| GitHub's restriction of who can push | https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches#restrict-who-can-push-to-matching-branches |
