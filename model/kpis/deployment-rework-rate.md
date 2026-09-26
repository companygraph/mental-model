---
source: Local
owner: Owner
measures: Delivery
unit: percent of deployments
direction: lower
read-with:
  - Deployment Frequency
---

# Deployment Rework Rate

> The share of deployments that were not planned and happened because of an incident in production.

## How it is measured

A deployment is a merge to `main` in a repository whose workflows publish one of this model's surfaces — the companygraph.io website, which GitHub Pages publishes, and the mcp.companygraph.io MCP server and the chat.companygraph.io chat, which that repository's deploy and chat workflows publish — and a release of meta-model, mcp-server, chat-server or the Obsidian plugin, because a release is what someone adopting CompanyGraph installs. A merge counts once, however many of its workflows publish. The MCP Registry listing, republished when the MCP server's repository tags a release, is not a deployment.

The deployments of a calendar month in UTC made because something in production was wrong or an installed release was broken, a revert, a hotfix, an emergency re-pin or an unplanned patch release, divided by all deployments of that month. Deployments and their times are read from the merges to `main` in the GitHub history of companygraph/companygraph.github.io and companygraph/mcp-companygraph-io; their publishing runs are GitHub Pages' own `pages-build-deployment` runs for the site and mcp-companygraph-io's `deploy` and `chat` workflow runs on `main`; a release is read from the GitHub releases of companygraph/meta-model, companygraph/mcp-server, companygraph/chat-server and companygraph/obsidian-plugin. Whether a deployment is rework is read from why it was made, which its pull request says, not from its size.

## What it can hide

It falls when fixes are held back and shipped inside planned work, so the incident lasts longer and the rate looks better. Deployment Frequency, read beside it, shows whether planned deployments are still going out.

## References

| What | URL |
| --- | --- |
| DORA's definition | https://dora.dev/guides/dora-metrics/ |
