---
id: 01a1128e-a262-7d5b-bec5-d57aaf015a1d
source: Local
decided: 2026-10-06
kind: Data protection
status: Standing
by: Owner
---

# The sessions we build CompanyGraph in are not used to train Anthropic's models

> We keep “Help improve our AI models” switched off on the Claude account on which the Owner and the agents build CompanyGraph, so the chats and coding sessions in which CompanyGraph is specified, built and reviewed, including work in an instance of a company that adopts it, are not used to train or improve Anthropic's models.

## The question

The Claude account the work is done on offers a setting that lets Anthropic use its chats and coding sessions to train and improve its models, and it covers Claude Code when it runs on that account. Every session in which the meta-model, the tooling and this model are specified, built and reviewed goes through that account, and so does work in an instance of a company that adopts CompanyGraph, which reads and writes that company's facts. It had to be decided before such work runs on the account, because a session used for training cannot be taken back.

## Alternatives

| Option | Why not |
| --- | --- |
| Leave the setting on | Anthropic could train on a session that read or wrote an adopting company's facts, which are that company's and not ours to give, and we could no longer tell a company which of its facts left for training and which did not. |
| Separate accounts, one with the setting on for our own public work and one with it off for work in an instance | Whoever opens a session would draw the line between the two each time, and a session that reads the meta-model and an instance at once falls on both sides of it; one setting, held one way, is a line nobody has to draw. |

## Why

What anyone writes in an instance stays theirs, and that holds only if the sessions that touch an instance do not pass its contents on for a purpose the company never chose. With the setting off, the answer to a company asking whether its model trains anyone's AI is one sentence, true for every session on the account. What we give up is small: our own work is published under an open license in public repositories, so keeping the sessions behind it out of training withholds the drafts and the reasoning, not the work.

## Consequences

We are committed to keeping the setting off on this account, and to reading it again when Anthropic changes its consumer terms or asks for the choice again, because one careless answer to that prompt turns it back on. The call does not make Anthropic our data processor for these sessions and changes nothing about how it handles them otherwise: Anthropic still receives and processes every request under its own terms and keeps what it keeps for as long as those terms say. Its terms keep two exceptions even with the setting off, a conversation flagged for safety review and one given thumbs-up or thumbs-down feedback, and either can still be used. The Anthropic page in this model covers the chat's requests through the API, under a processing agreement, and not this account. The call covers this one account; another account brought to the work is a question of its own. It stays right for as long as Anthropic's terms honor the setting and the work is done on this account.

## References

| What | URL |
| --- | --- |
| Anthropic's consumer terms and the model training setting | https://www.anthropic.com/news/updates-to-our-consumer-terms |
| When Anthropic uses data for model training | https://privacy.claude.com/en/articles/10023580-is-my-data-used-for-model-training |
