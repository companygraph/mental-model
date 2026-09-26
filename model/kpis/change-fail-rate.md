---
source: Local
owner: Owner
measures: Delivery
unit: percent of deployments
direction: lower
read-with:
  - Deployment Frequency
---

# Change Fail Rate

> The share of deployments that need immediate intervention once they are in production.

## How it is measured

A deployment is a merge to `main` in a repository whose workflows publish one of this model's surfaces — the companygraph.io website, which GitHub Pages publishes, and the mcp.companygraph.io MCP server and the chat.companygraph.io chat, which that repository's deploy and chat workflows publish — and a release of meta-model, mcp-server, chat-server or the Obsidian plugin, because a release is what someone adopting CompanyGraph installs. A merge counts once, however many of its workflows publish. The MCP Registry listing, republished when the MCP server's repository tags a release, is not a deployment.

The deployments of a calendar month in UTC that were followed, before the next planned change to the same surface or package, by a revert, a fix or a re-pin made because of them, divided by all deployments of that month. Deployments and their times are read from the merges to `main` in the GitHub history of companygraph/companygraph.github.io and companygraph/mcp-companygraph-io; their publishing runs are GitHub Pages' own `pages-build-deployment` runs for the site and mcp-companygraph-io's `deploy` and `chat` workflow runs on `main`; a release is read from the GitHub releases of companygraph/meta-model, companygraph/mcp-server, companygraph/chat-server and companygraph/obsidian-plugin. A failure is what a visitor, an agent or a check against the live surface met, or what an instance that installed the release met, not a workflow run that failed before publishing anything.

## What it can hide

It falls when fewer changes ship, and when a failure is folded into the next planned change instead of being named as one. Deployment Frequency, read beside it, shows the first; the second shows only if failures are named when they happen.

## References

| What | URL |
| --- | --- |
| DORA's definition | https://dora.dev/guides/dora-metrics/ |
