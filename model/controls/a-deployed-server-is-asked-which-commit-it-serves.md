---
id: 01a13b64-5acc-7b29-a65e-6b7fa3148c60
source: Local
kind: detective
mode: automated
enforces:
  - A state is read again before it is relied on
---

# A deployed server is asked which commit it serves

> After every deploy of mcp.companygraph.io the run asks the live server which commit of the model it answers at, and fails unless it is the commit the repository pins.

## How it is carried out

The deploy job that mcp.companygraph.io's workflow calls from the MCP server, on every push to main, once Terraform has applied: it calls the live server's own `list_types` tool, reads the commit every answer names under `model`, and fails unless it is the commit `source.json` pins. A deploy that applied cleanly but left an earlier revision serving, or one built from another commit, then turns the run red instead of reading as done.

## Applies to

| Type | Entity | Owner |
| --- | --- | --- |
| phase | Integrate | Delivery |

## References

| What | URL |
| --- | --- |
| The deploy job and its check | https://github.com/companygraph/mcp-server/blob/main/.github/workflows/deploy-google.yml |
| The workflow that calls it | https://github.com/companygraph/mcp-companygraph-io/blob/main/.github/workflows/deploy.yml |
