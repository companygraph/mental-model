---
source: Local
owner: Owner
measures: Delivery
unit: deployments per week
direction: higher
read-with:
  - Change Fail Rate
---

# Deployment Frequency

> How often a change reaches production.

## How it is measured

A deployment is a merge to `main` in a repository whose workflows publish one of this model's surfaces — the companygraph.io website, which GitHub Pages publishes, and the mcp.companygraph.io MCP server and the chat.companygraph.io chat, which that repository's deploy and chat workflows publish — and a release of meta-model, mcp-server, chat-server or the Obsidian plugin, because a release is what someone adopting CompanyGraph installs. A merge counts once, however many of its workflows publish. The MCP Registry listing, republished when the MCP server's repository tags a release, is not a deployment.

The number of deployments in a calendar week. A workflow run that failed and published nothing is not a deployment.

## What it can hide

It rises when one change is split into several deployments and when something ships that did not need to; the first is the point and the second is noise. A rise bought with rushed changes shows in Change Fail Rate. A week without deployments reads the same whether nothing was ready or nothing was worth shipping.

## References

| What | URL |
| --- | --- |
| DORA's definition | https://dora.dev/guides/dora-metrics/ |
