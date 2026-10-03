---
id: 01a1008f-79fe-7b6e-a781-fe4de5024498
source: Local
owner: Owner
assesses:
  - Main takes a change only through a green, current pull request
serves:
  - Every gate an agent's work passes is held by a person
unit: merges per week
direction: lower
read-with:
  - Change Fail Rate
---

# Merges Past Their Checks

> The merges that reached a default branch of ours in one week while a required check had not passed.

## How it is measured

GitHub records a rule suite with the result `bypass` each time a change reaches a default branch although a rule of its ruleset did not pass, which only an admin can do. Every Monday, the `kpi` workflow of companygraph/mcp-companygraph-io reads the ISO week that ended, Monday 00:00 to Monday 00:00 UTC, across the companygraph organization's repositories with the organization's GitHub App, and classifies each bypass from its pull request. A merge counts here when a required check had not completed with success by the merge — still queued, running or failed — or when the change had no pull request, broke a rule other than the required checks, or could not be read. A merge whose branch was only behind main, with every required check passed, does not count. The week's object, `ruleset-bypasses/<year>-W<week>.json` in the bucket `kpi-reports-companygraph-io-mcp`, holds this count as `past_checks`, beside `behind_main` and the total.

## What it can hide

A repository with no ruleset is never evaluated, and a check that is not required does not count. A merge behind main is not counted although its checks ran against an older main. A required check that a path filter skipped counts as not passed although nothing was skipped on purpose. Where the App cannot read a ruleset's history, the required checks are counted from the rule suite at the merge, and a check required today but not then can, if it ran green, stand in for one that never started. Change Fail Rate, read beside it, shows whether these merges failed more often than the rest.

## References

| What | URL |
| --- | --- |
| The weekly workflow | https://github.com/companygraph/mcp-companygraph-io/blob/main/.github/workflows/kpi.yml |
| Where the values are kept | https://console.cloud.google.com/storage/browser/kpi-reports-companygraph-io-mcp/ruleset-bypasses |
| GitHub's rule suites | https://docs.github.com/en/rest/repos/rule-suites |
