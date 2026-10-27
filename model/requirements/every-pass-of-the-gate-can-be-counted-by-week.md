---
id: 01a13dc2-94f1-7ade-8355-8190f03c4780
source: Governance research
source-id: GD-35
kind: functional
modality: must
realization: Partly released
---

# Every pass of the gate can be counted by week

> Every change applied, every required check gone past and every change of rights is kept in a log a scheduled job can read by week.

## Why

The KPIs that measure the gate, Merges Past Their Checks and Change Fail Rate, are counted from that log and from nothing else.

## Fit criterion

A job that reads only the log counts a week's applied changes and the checks gone past as the KPI reports them. Today GitHub's audit log and rule suites, read by the weekly `kpi` workflow, meet it.

## Applies to

| Type | Entity |
| --- | --- |
| feature | Checks an instance runs |

## Realization

companygraph/mental-model at origin/main holds only the `companygraph` and `conventions` workflows and no weekly count. The deployment `mcp-companygraph-io` at its deployed commit runs `kpi.yml` every Monday, calling mcp-server v0.69.0's `kpi-google.yml`, which reads the organization's rule suites with a read-only GitHub App through `bin/bypasses.mjs`, classifies each bypass of a default branch as behind main or past its checks, and writes the week's Merges Past Their Checks object to the project's bucket; tests check the ISO week, that only bypasses inside the week count, that an unreadable repository is unread and not zero, and the classification. The log itself is GitHub's rule suites. Nothing released counts a week's applied changes or the changes of rights, so the Change Fail Rate and the rights half of the criterion are not met.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `bin/bypasses.mjs` | satisfies | https://github.com/companygraph/mcp-server/blob/v0.69.0/bin/bypasses.mjs |
| `test/bypasses.test.mjs` | satisfies | https://github.com/companygraph/mcp-server/blob/v0.69.0/test/bypasses.test.mjs |
| `.github/workflows/kpi.yml` | satisfies | https://github.com/companygraph/mcp-companygraph-io/blob/868854216c611db2ff536820d04f45b463b19c08/.github/workflows/kpi.yml |
