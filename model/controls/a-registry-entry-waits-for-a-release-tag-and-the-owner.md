---
id: 01a13b60-837c-72ae-8285-e9410ccc7309
source: Local
kind: preventive
mode: automated
enforces:
  - The Owner's word merges
---

# A registry entry waits for a release tag and the Owner

> A server's entry in the MCP registry is published only from a release tag and only once the Owner has approved that run, because the key that signs it is held where no other run can reach it.

## How it is carried out

GitHub's `registry` environment on mcp.companygraph.io's repository, on every run of the publish workflow: it lets a job in only from a tag matching `v*`, and holds that job until the Owner approves it. The key that signs the entry is a secret of the environment and of no other, so a run from a branch, or one nobody approved, never holds it and cannot publish. A repository admin may bypass the review, which is the Owner's account, so an agent working under it is held by An agent's permissions refuse a merge it was not given.

## Applies to

| Type | Entity | Owner |
| --- | --- | --- |
| phase | Integrate | Delivery |

## References

| What | URL |
| --- | --- |
| GitHub's deployment environments | https://docs.github.com/en/actions/how-tos/deploy/configure-and-manage-deployments/manage-environments |
| The publish workflow | https://github.com/companygraph/mcp-companygraph-io/blob/main/.github/workflows/publish.yml |
| The registry job it calls | https://github.com/companygraph/mcp-server/blob/main/.github/workflows/registry.yml |
