---
id: 01a0ffcb-a8db-75a8-b16d-aee6277e8878
source: Local
kind: preventive
mode: automated
enforces:
  - A check counts only when its output was seen
  - A state is read again before it is relied on
  - A commit keeps the author it was made with
---

# Main takes a change only through a green, current pull request

> The default branch of each of our repositories refuses a push, and takes a change only through a pull request whose named checks pass on a branch that is up to date with it, merged with a merge commit.

## How it is carried out

GitHub's ruleset on each repository's default branch, on every attempt to change it: it refuses a force push and a deletion, takes a change only through a pull request, requires the named checks to pass, and requires the branch to be up to date with the default branch, so a pull request whose base has moved shows as behind until main is merged into it. A pull request merges only with a merge commit: in each repository either the ruleset allows no other merge method or the repository's settings turn squash and rebase off, so a commit reaches main under the author it was made with. The ruleset lets a repository admin bypass it.

## Applies to

| Type | Entity | Owner |
| --- | --- | --- |
| phase | Integrate | Delivery |
| phase | Integrate | Contribution |

## References

| What | URL |
| --- | --- |
| GitHub rulesets | https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/about-rulesets |
| GitHub merge methods | https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges/about-merge-methods-on-github |
