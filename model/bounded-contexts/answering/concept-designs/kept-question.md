---
id: 01a10042-5f3a-71bc-af0e-2f644bc7246a
source: Local
kind: value object
---

# Kept question

> What is kept of one message once it has its answer or its refusal, for the owner to read what the chat was asked and whether the model could answer it. It holds the visitor's question and never their address, a header or a word of the answer.

## Attributes

| Attribute | Term | Type | Many | Description |
| --- | --- | --- | --- | --- |
| Question | | string | | The visitor's last turn as it was sent, trimmed |
| Page language | | language | | The page's language, `en` or `de`, where it is one the interface names, else empty |
| Cited | | id | yes | The entities the answer cited, in order |
| Calls | | number | | How many tool calls the answer made |
| Empty | | number | | How many of those found nothing: refused, an error, or a list with no rows |
| Rounds | | number | | How many requests the model answered |
| Refused | | string | | The refusal's code, empty where the model answered |
| Claims | | number | | How many claims the answer made, where it was checked; empty where it was not |
| Not carried | | number | | How many of those were judged anything but `supported` or `says-nothing`, where it was checked; empty where it was not |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/chat-server/blob/main/lib/http.mjs |
| The interface | https://github.com/companygraph/chat-server/blob/main/docs/INTERFACE.md |
