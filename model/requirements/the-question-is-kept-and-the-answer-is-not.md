---
id: 01a1312d-2629-72e5-9208-31b5c5db8047
source: Local
kind: constraint
modality: must
realization: Released
---

# The question is kept and the answer is not

> A chat keeps of each message one line, the question itself and whether the model could answer it, never with an address and never past ninety days, and keeps no answer.

## Why

The one quantity the company watches is whether an answer rested on the model, and that is read from the question and the entities cited, not from the answer's text; an answer kept would be a record of a conversation the visitor was promised lives in their tab and ends with it.

## Fit criterion

The kept line holds the question, its language, the entities the answer cited, how many tool calls were made and how many found nothing, and whether the fence refused, and no field holds the answer or an address; a line older than ninety days is gone.

## Applies to

| Type | Entity |
| --- | --- |
| feature | A visitor asks the model |

## Realization

Once a message has its answer or refusal the service writes one line holding the question, its language, the model and effort, the cited ids, the call and empty counts, the rounds, the refusal code and, where the answer was checked, the claim counts. A test compares the line's keys and values exactly and checks that neither the sender's address nor a word of the answer is in it. The log bucket is created with a retention of 90 days on Google and 90 days on Azure, in Terraform; no test observes that a line older than ninety days is gone, and the Terraform tests in the release cover sign-in and the verdict only.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `test/http.test.mjs` | satisfies | https://github.com/companygraph/chat-server/blob/v0.38.3/test/http.test.mjs |
| `lib/http.mjs` | satisfies | https://github.com/companygraph/chat-server/blob/v0.38.3/lib/http.mjs |
| `deploy/google/terraform/questions.tf` | satisfies | https://github.com/companygraph/chat-server/blob/v0.38.3/deploy/google/terraform/questions.tf |

## References

| What | URL |
| --- | --- |
| The interface, with the kept line's fields | https://github.com/companygraph/chat-server/blob/main/docs/INTERFACE.md |
