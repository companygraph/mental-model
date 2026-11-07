---
id: 01a1b577-35b9-7c33-8f5b-3e50bff16675
source: Local
kind: Deployment
owner: Owner
processor: Microsoft Azure
part-of: Azure Container Apps
environment: Production
---

# Chat server on Azure

> Answers the questions a visitor sends once the chat on companygraph.io is set to Azure, from what the MCP server on Azure returns, has a language model write each answer, reached by a federated identity and no key, and logs each question it answers or refuses; it checks no answer.

## Connects to

| System | As | Service | Carries | Via |
| --- | --- | --- | --- | --- |
| MCP server on Azure | Streamable HTTP | MCP endpoint | Entity | HTTPS |
| Claude API | Messages API | | | HTTPS |
| id.blust.ch | OpenID Connect | | | HTTPS |

## Holds

| Concept | Data object | Access |
| --- | --- | --- |
| Conversation | Question log | writes |
| Reader | Reader's month | writes |

## References

| What | URL |
| --- | --- |
| The server's source and documentation | https://github.com/companygraph/chat-server |
| The interface the chat answers over | https://github.com/companygraph/chat-server/blob/main/docs/INTERFACE.md |
| The deployment's pins, configuration and infrastructure | https://github.com/companygraph/mcp-azure-companygraph-io |
