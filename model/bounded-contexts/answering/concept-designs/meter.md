---
id: 01a10042-5f9f-7bfa-8044-330e4216f841
source: Local
kind: entity
---

# Meter

> What the chat may spend on the model: the month's ceiling a deployment writes down and the day's share of it, beside what the day and the month have spent, counted in input-equivalent tokens and kept outside any one instance so every instance reads the same standing.

## Attributes

| Attribute | Type | Description |
| --- | --- | --- |
| Month ceiling | input-equivalent tokens | What the month may spend, as the deployment states it |
| Day share | input-equivalent tokens | What one day may spend, a tenth of the month's ceiling |
| Day spent | input-equivalent tokens | What today has spent, counted from midnight UTC |
| Month spent | input-equivalent tokens | What this month has spent, counted from the first at midnight UTC |
| Closed | boolean | Whether the owner switched the chat off |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/chat-server/blob/main/lib/meter.mjs |
