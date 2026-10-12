---
id: 01a12eb2-fad9-752e-a440-0a85a6867456
source: Local
rank: 30
---

# Production

> Where companygraph.io, the MCP server and the chat server serve their visitors, the one environment CompanyGraph runs, deployed to on every merge and never by hand.

## What it means

The MCP server and the chat server run here as containers on Cloud Run, reached at mcp.companygraph.io and chat.companygraph.io, and the Site build's pages are served here by GitHub Pages at companygraph.io. CompanyGraph's own seats deploy to it by merging to the repository that pins what runs: a merge to mcp-companygraph-io builds and releases the servers, a merge to companygraph.github.io publishes the site. Nobody deploys to it by hand, and nothing runs here that a merge did not put there. It holds the public model at one pinned commit, and the Question log the chat writes, which is what real visitors asked and the only data here that is anyone's. A developer's machine, where a server runs against a checkout before a change ships, is not it, and no test stage stands between the two.

## References

| What | URL |
| --- | --- |
| The pipeline that deploys the servers | https://github.com/companygraph/mcp-companygraph-io/blob/main/.github/workflows/deploy.yml |
| The pipeline that publishes the site | https://github.com/companygraph/companygraph.github.io/blob/main/.github/workflows/ci.yml |
| The site | https://companygraph.io |
| The MCP server's page | https://mcp.companygraph.io |
