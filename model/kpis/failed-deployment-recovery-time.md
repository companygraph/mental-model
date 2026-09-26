---
source: Local
owner: Owner
measures: Delivery
unit: hours
direction: lower
read-with:
  - Change Fail Rate
---

# Failed Deployment Recovery Time

> The time it takes to recover from a deployment that fails and needs immediate intervention.

## How it is measured

A deployment is a merge to `main` in a repository whose workflows publish one of this model's surfaces — the companygraph.io website, which GitHub Pages publishes, and the mcp.companygraph.io MCP server and the chat.companygraph.io chat, which that repository's deploy and chat workflows publish — and a release of meta-model, mcp-server, chat-server or the Obsidian plugin, because a release is what someone adopting CompanyGraph installs. A merge counts once, however many of its workflows publish. The MCP Registry listing, republished when the MCP server's repository tags a release, is not a deployment.

For each failed deployment, as Change Fail Rate counts them, the time from that deployment going live to the deployment that restores the surface going live, whether a revert, a fix, a re-pin to an earlier release or the release that supersedes a failed one being published. The value is the median over a calendar quarter in UTC. Deployments and their times are read from the merges to `main` in the GitHub history of companygraph/companygraph.github.io and companygraph/mcp-companygraph-io; their publishing runs are GitHub Pages' own `pages-build-deployment` runs for the site and mcp-companygraph-io's `deploy` and `chat` workflow runs on `main`; a release is read from the GitHub releases of companygraph/meta-model, companygraph/mcp-server, companygraph/chat-server and companygraph/obsidian-plugin. A failure no deployment caused, a provider's outage, is not counted.

## What it can hide

It shortens when every failure is reverted rather than fixed, which restores the surface and leaves the change undone, so the change comes back as rework. Failures are rare here, so a quarter's median can rest on one or two events, and one slow recovery moves it a long way.

## References

| What | URL |
| --- | --- |
| DORA's definition | https://dora.dev/guides/dora-metrics/ |
