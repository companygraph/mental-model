---
id: 01a1256e-95a8-7252-a79b-d83322045bb1
source: Local
kind: Deployment
owner: Owner
processor: Google Cloud
part-of: Cloud Run
---

# Chat server

> Answers the questions a visitor asks on companygraph.io from what the MCP server returns, has a language model write each answer and a judge check its claims, and logs each question it answers or refuses.

## Connects to

| System | As | Service | Carries | Via |
| --- | --- | --- | --- | --- |
| MCP server | Streamable HTTP | MCP endpoint | Entity | HTTPS |
| Claude API | Messages API | | | HTTPS |
| TypeSafe | System One API | | | HTTPS |

## Holds

| Concept | Data object | Access |
| --- | --- | --- |
| Conversation | Question log | writes |

## References

| What | URL |
| --- | --- |
| The server's source and documentation | https://github.com/companygraph/chat-server |
| The interface the chat answers over | https://github.com/companygraph/chat-server/blob/main/docs/INTERFACE.md |
| The deployment's pins, configuration and infrastructure | https://github.com/companygraph/mcp-companygraph-io |
