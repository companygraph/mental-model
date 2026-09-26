---
source: Local
owner: Owner
measures: Delivery
unit: hours
direction: lower
read-with:
  - Change Fail Rate
---

# Change Lead Time

> The time a change takes from being committed to version control to running in production.

## How it is measured

A deployment is a merge to `main` in a repository whose workflows publish one of this model's surfaces — the companygraph.io website, which GitHub Pages publishes, and the mcp.companygraph.io MCP server and the chat.companygraph.io chat, which that repository's deploy and chat workflows publish — and a release of meta-model, mcp-server, chat-server or the Obsidian plugin, because a release is what someone adopting CompanyGraph installs. A merge counts once, however many of its workflows publish. The MCP Registry listing, republished when the MCP server's repository tags a release, is not a deployment.

For each deployment, the time from the earliest commit it carries that no earlier deployment carried to the moment it is live, or for a release, published; a change to the model counts from its commit in companygraph/mental-model to the deployment of the re-pin that carries it. The value is the median over the deployments of a calendar month in UTC, read from the merges to `main` and their times in the GitHub history of companygraph/companygraph.github.io and companygraph/mcp-companygraph-io, from `pages-build-deployment` runs for the site and mcp-companygraph-io's `deploy` and `chat` runs on `main`, and, for a release, from the commit history and GitHub releases of companygraph/meta-model, companygraph/mcp-server, companygraph/chat-server and companygraph/obsidian-plugin.

## What it can hide

It shortens when changes get smaller and when review gets thinner, and only the first is progress. Thinner review shows as a higher Change Fail Rate, which is why the two are read together. A median also hides the change that waited a week behind a re-pin.

## References

| What | URL |
| --- | --- |
| DORA's definition | https://dora.dev/guides/dora-metrics/ |
