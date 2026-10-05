---
id: 01a10a7b-ba62-7bcf-9dce-4e1a261e27fa
source: Local
owner: Owner
measures: Answering
serves:
  - An agent answers as well as the person who runs the company
unit: percent of checked claims per week
direction: higher
read-with:
  - Grounded Answer Rate
---

# Carried Claim Rate

> The share of a week's claims, in the answers a chat checked, that the evidence the answer was written from carries.

## How it is measured

The chats this KPI counts are the surfaces of this model that answer a visitor's question from it and check their answers. A claim is a sentence, a list item or a table row of an answer. Where a deployment checks, each claim is judged against the text of the tool answers that carried the entities it names, exactly as the model was given it, and the kept line of the message counts its `claims` and its `unsupported`: those judged `partial`, `contradicted`, `absent`, `withheld`, `unnamed` or `unsourced`. A message whose check could not run, or that was refused, carries neither count and is left out.

Each chat's weekly report sums both counts over the answers it checked in the ISO week that ended, Monday midnight UTC to the next, under its Claims section; the value, read per chat, is the week's claims less those not carried, divided by its claims. Every verdict counts whatever its probability, so the value does not move with the threshold above which the chat marks a claim, and a German answer counts though the chat marks none.

## What it can hide

A claim is judged against what the tools returned, so a claim that repeats a page which is itself wrong counts as carried: the rate says the answers kept to the model, not that the model is true. It rises when answers say less, since an answer with fewer claims has fewer to miss, and a chat that stops using the tools makes no claims the check can count; Grounded Answer Rate, read beside it, shows answers that no longer rest on the model. A claim judged `partial` counts as not carried however much of it was. And the judge is another company's model at a release of its own, so a new release can move the rate with no answer changed; a week that moves without a change to the chat or the model is read against the judge's release first.

## References

| What | URL |
| --- | --- |
| The kept line's `claims` and `unsupported` | https://github.com/companygraph/chat-server/blob/main/docs/INTERFACE.md |
| The design of the check and what was measured before it was trusted | https://github.com/companygraph/chat-server/blob/main/docs/superpowers/specs/2026-09-26-the-answer-is-checked-design.md |
| The chat.companygraph.io chat's weekly report, which sums the counts | https://github.com/companygraph/mcp-companygraph-io/blob/main/.github/workflows/report.yml |
