---
id: 01a10042-5f07-7abf-b76a-72c457dc2cfc
source: Local
root: Message
members:
  - Cite
  - Name
  - Fence
  - Claim
decisions:
  - A model is written in one language
  - A model that writes no text checks every claim of the chat's answers
---

# Message

> A message's answer stays inside its fence, cites and names each entity once, and ends either with what it spent and at which commit or, where the visitor left, with nothing more.

## Invariants

| Label | Invariant |
| --- | --- |
| INV-A1 | A message reaches the model only when its turns alternate, begin and end with the visitor, and no visitor turn is longer than the fence allows after trimming; any other is refused before a request is made. |
| INV-A2 | No more turns than the fence allows reach the model, and the first that reaches it is the visitor's. |
| INV-A3 | A message takes no more tool rounds than the fence allows, and its last request can call no tool and says so in words. |
| INV-A4 | A request that answers with neither text nor a call, and was not cut by the output limit, is asked once more as the last request, and never a second time. |
| INV-A5 | An entity is cited at most once in a message, however many rounds fetch it. |
| INV-A6 | An entity is named at most once in a message, never where the message cites it, and never past the fence's number of names. |
| INV-A7 | The model reads a tool's answer cut to the fence's length, and of a diagram only the titles and types it drew and the relations it listed, never its source. |
| INV-A8 | Every request tells the model to answer in the language the last message's words are in, even where their grammar is a learner's, and in the page's language only where they do not tell. |
| INV-A9 | Every request after a tool round ends with the naming note, which quotes the visitor's last message and asks for an entity's name in the answer's language before its exact title. |
| INV-A10 | An answered message ends with one done event naming the host's commit and what the message spent, marked cut where the output limit stopped it; a message whose visitor left sends nothing after the request in flight. |
| INV-A11 | A message keeps one line of itself, with its answer or its refusal, and a message refused as malformed, too long or foreign keeps none. |
| INV-A18 | A message's claims are checked after its last text and before its done event, and a check that cannot run within its budget sends no verdict and changes neither the answer nor what follows it. |
| INV-A19 | A claim's evidence is the text of the tool answers that carried the entities it names, cut where the model's own was cut, and nothing more. |
| INV-A20 | A claim that writes the title of an entity no tool returned in the message is `unsourced` and carries no probability, and a claim that says the model holds nothing where a tool call found something is `withheld`. |
| INV-A21 | A checked message's kept line counts its claims and those not carried, and a message whose check did not run carries neither count. |

## Handled commands

| Command | Emits | When | Description |
| --- | --- | --- | --- |
| Answer a message | | | Puts the conversation to the model with the host's tools and streams the answer, citing and naming as it goes; refuses before the first request what the fence or the meter refuses |
| Stop answering | | | The visitor closed the page: asks no further round, settles the meter, and sends nothing more |
| Keep the question | | | Writes the one line kept of the message once it has its answer or its refusal |
| Check the answer | Answer checked | the deployment checks its answers and the check ran within its budget (INV-A18) | Reads each claim back against its evidence after the last text, and sends nothing where the check cannot run |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/chat-server/blob/main/lib/loop.mjs |
