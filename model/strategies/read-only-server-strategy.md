---
source: Local
adopted: 2026-09-16
serves:
  - An agent answers as well as the person who runs the company
upholds:
  - Run on what we publish
  - Adoption is not taxed
---

# Read-Only Server Strategy

> An agent reaches a company's model through a server that only reads it, answers at one named commit, and adds nothing of its own.

## The approach

The server reports what the model says and stops there. Every answer names the commit it was read at, so an answer can be checked against the same bytes later and two answers given a week apart can be told apart. Its tools are the vocabulary's own questions — which types a company declares, what one entity says, what evidence a claim rests on, which rule governs a page — so an agent asks the model the way the model is shaped rather than searching its text and hoping.

It serves any instance, not only ours, and the deployment we run points at the reference instance at a pinned commit. That is what keeps the server honest: the first model it has to answer about is one whose every claim we can be held to.

Nothing is summarized away. Where a claim has evidence the answer carries the evidence, and where it has none the answer says so rather than filling the gap with something plausible. The server is published under the same terms as everything else, because an access layer that costs money is a seat count wearing a different name.

A company runs all of it itself. Its model is a repository it keeps where it keeps its code, and the server and the chat beside it are deployed into the company's own cloud project from the parts this project publishes, so nothing a company writes passes through us. What leaves is what a chat visitor sends, which goes to the language model the deployment names: on Vertex AI in the company's own project, or to Anthropic under the company's own key.

## What it rules out

No write path: an agent cannot change a company's model through the server, so no company has to decide whether to trust one with that. No embedding index as the way in — a retrieval layer answers with a paraphrase, and a paraphrase cannot be held to the evidence the model attached to the claim. No answer without a commit behind it, which rules out answering about a model's current state in general. No reasoning the server does that the model cannot show, however much more useful the inferred answer would be. And no hosted model bundled with it: the server reads an instance a company keeps, and a company that would have to hand over its model to be served has been charged for adoption.

## What would show it is working

The same question put to the person who runs a company and to an agent reading its model, and the two answers agreeing — with the agent's followable to the page it came from. That test runs in a minute and fails visibly, which is what makes it an instrument rather than a verdict. Answers that name no commit, which should be none and are countable. And an instance nobody here wrote being served without a change to the server, because a server that needs adjusting per model has learned one company rather than the vocabulary.
