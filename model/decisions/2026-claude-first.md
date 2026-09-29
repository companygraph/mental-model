---
source: Local
decided: 2026-09
kind: Architecture
status: Standing
by: Owner
serves:
  - Whether this is a business is answered
  - A company keeps its model with whichever agent it chooses
upholds:
  - Run on what we publish
---

# Claude is the first agent an instance supports, and not the only one

> An instance's skills are written for Claude first, so the idea can be validated before the work of supporting every agent is spent on it; the other agents follow, and supporting Claude alone is a stage and not the design.

## The question

Which agent the skills an instance ships are written for, when `init` first installed them. Each agent looks for its procedures in its own place and its own form, so the first skills had to be written for one agent or for several. It had to be decided then because the idea was not validated yet: whether a company keeps a model at all is the question the ideas page puts, and every agent supported before that is answered is work spent on an idea that may get a clean no.

## Alternatives

| Option | Why not |
| --- | --- |
| Every agent from the first release: Claude, ChatGPT and Gemini | Three places for every procedure and three agents to test every skill against, all before anyone outside had kept a model, and multiplied by every skill that changed while the idea was still moving. |
| No skills, only the vocabulary and the checks | The procedures that build an instance from documents or from a web address are the judgment no script makes; without them nobody could try the idea at the cost the ideas page asks about. |

## Why

The work is validating the idea, and a skill written for one agent validates it as well as a skill written for three: what is being tested is whether a company keeps its model, not which agent it keeps it with. Claude took the first place because it is the agent our own three instances are written and kept with, so every skill runs on real models before it ships.

## Consequences

An instance made today can be kept with Claude and no other agent, and a company working with another agent reads that as "not for us"; the command-line page says so and says others are planned. `init` already takes the agent as an option, so adding one is a release and not a redesign. For the call to stay right, the model has to stay plain Markdown that no agent owns, and no skill may come to depend on something only Claude can do, or the second agent becomes a rewrite. The call ends when the idea is validated or work on a second agent starts, whichever comes first, and a later decision supersedes it.

## References

| What | URL |
| --- | --- |
| The ideas and the questions validation has to answer | https://blust.ch/ideas/ |
| The note that Claude is the only agent today | https://companygraph.io/cli/ |
