---
id: 01a1080d-caaa-7e4d-86b6-9c83292095b8
source: Local
decided: 2026-10-04
kind: Data protection
status: Standing
by: Owner
upholds:
  - Run on what we publish
---

# The chat's answers are written in the US

> The chat asks the Anthropic API to run every request in the United States, so the one country a visitor's message goes to can be named, on the privacy page and in the model.

## The question

The chat called the Anthropic API without naming a region, and Anthropic then runs a request in any geography it chooses. The Swiss data protection act asks a privacy page to name the state personal data is disclosed to, and the model's Anthropic page asks for its countries; with no region set, neither could be named truthfully.

## Alternatives

| Option | Why not |
| --- | --- |
| Leave the region to Anthropic | The country a visitor's message goes to could not be named, which is what the page and the model are for. |
| Claude on Vertex AI in a European region, beside the chat in Zürich | The project holds no Vertex quota for it, so it could not be run. |

## Why

Anthropic offers two settings, any geography or the United States, and the data it keeps is stored in the United States already. Naming the United States makes every part of a request happen in one country the transfer clauses already cover.

## Consequences

Every request costs 1.1 times the standard rate. The deployment's chat.json names the region and chat-server sends it with every request; once the owner restricts the Console workspace to the United States, a change in code cannot widen it. The call stays right for as long as Anthropic offers no region closer to Switzerland; if it does, the call is weighed again.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| data-processor | Anthropic | | its countries are now exact |
| processing-activity | Answering in the chat | | its messages are processed in the US |

## References

| What | URL |
| --- | --- |
| The deployment's chat configuration | https://github.com/companygraph/mcp-companygraph-io/blob/main/chat/chat.json |
| Anthropic's data residency | https://platform.claude.com/docs/en/manage-claude/data-residency |
| The chat-server release that names the region | https://github.com/companygraph/chat-server/releases/tag/v0.27.0 |
