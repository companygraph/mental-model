---
id: 01a10a7e-285a-7b7c-8224-943f38e5655e
source: Local
decided: 2026-10-03
kind: Architecture
status: Standing
by: Owner
serves:
  - An agent answers as well as the person who runs the company
---

# A model that writes no text checks every claim of the chat's answers

> We check each claim of every answer the chat gives against the tool answers the chat's model was given, with TypeSafe's Jev, a model that picks one of a fixed set of verdicts with a probability and writes no text; the check changes no answer, and the chat marks a claim only above a threshold measured on real answers before it is set.

## The question

Whether anything checks that an answer says what the entities it names say. The chat named the entity each claim rests on, and nothing held the claim to it: a claim could name the right entity and state the wrong date, and neither the visitor nor the owner could tell. It had to be decided on October 3, 2026, when the design of the check had been measured against planted faults and left three choices open: whether the check runs at all, since it sends the answer to a party the privacy pages did not name; whether a German answer is checked before German is measured; and whether the chat marks a claim or only counts it.

## Alternatives

| Option | Why not |
| --- | --- |
| Ask the chat's own model to judge its answer | A text model grading its own kind of output, at the chat's price and latency, whose verdict is prose and can carry a claim of its own. |
| No check, with Grounded Answer Rate alone | The rate says whether an answer rested on the model and never whether it said what the model says, so a wrong date under a right link passes for the visitor and the owner alike. |
| Mark every claim the judge does not carry, from the first answer | Before a threshold is measured, a mark is a guess shown to a visitor as a finding. |
| A switch with which the visitor turns the check on | The kept counts would become a sample of the visitors who chose it. |

## Why

The check is a classification, whether the evidence carries the claim, and Jev answers one with a closed set of verdicts, each with a probability trained to be calibrated. A verdict can then be nothing but one the design names, a threshold can be read off a measured curve rather than chosen, and a judge that writes no prose cannot add a claim to the answer it judges. What reaches it is the chat's own sentences and the model's public text, never the visitor's question or address, which is what let the check run under a processor the privacy pages name.

## Consequences

TypeSafe processes the chat's answers, under its own key and a spend limit set at TypeSafe, outside the meter, and the privacy pages name it before any deployment turns the check on. Each deployment turns it on in its own configuration. A check that cannot run sends nothing and takes nothing from the answer, which it delays by at most the check's budget. The chat marks a claim only where its verdict is not carried and its probability is above the threshold the measurement gave; a German answer is checked and its verdicts kept, and none is marked until German is measured on its own. The kept line counts each answer's claims and those not carried, and Carried Claim Rate reads them. What we gave up is an answer that reaches the visitor without a second company's model in its path. The call stays right for as long as the verdicts stay calibrated against what is measured, and the judge writes no text.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| data-processor | TypeSafe | | made it one of ours |
| processing-activity | Answering in the chat | | changed it |
| kpi | Carried Claim Rate | | made it measurable |
| surface | chat.companygraph.io chat | | changed it |

## References

| What | URL |
| --- | --- |
| The design, the three choices and the measurement | https://github.com/companygraph/chat-server/blob/main/docs/superpowers/specs/2026-09-26-the-answer-is-checked-design.md |
| The `verdict` event and the kept line | https://github.com/companygraph/chat-server/blob/main/docs/INTERFACE.md |
| The deployment's switch and threshold | https://github.com/companygraph/mcp-companygraph-io/blob/main/chat/chat.json |
