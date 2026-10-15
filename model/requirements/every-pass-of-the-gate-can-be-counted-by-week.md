---
id: 01a13dc2-94f1-7ade-8355-8190f03c4780
source: Local
source-id: GD-35
kind: functional
modality: must
---

# Every pass of the gate can be counted by week

> Every change applied, every required check gone past, every change of rights and every purge is kept in a log a scheduled job can read by week.

## Why

The KPIs that measure the gate, Merges Past Their Checks and Change Fail Rate, are counted from that log and from nothing else.

## Fit criterion

A job that reads only the log counts a week's applied changes and the checks gone past as the KPI reports them. Today GitHub's audit log and rule suites, read by the weekly `kpi` workflow, meet it.

## Applies to

| Type | Entity |
| --- | --- |
| feature | Checks an instance runs |
