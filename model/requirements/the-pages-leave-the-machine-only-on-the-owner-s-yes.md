---
id: 01a1312c-c913-7d77-a07c-82a1f20adbc0
source: Local
kind: functional
modality: must
realization: Verified
---

# The pages leave the machine only on the owner's yes

> An instance's pages are sent to a service outside the machine only on the owner's yes to exactly the files, counts and digest shown for that run, and a yes given for another digest, an earlier run or another instance sends nothing.

## Why

Whether a company's pages go whole to an outside service is the owner's decision about their company's data, and it is a decision about these files and not about the judge in general. A run that sent on an earlier yes, or over a file list that changed after the yes, would send what nobody agreed to.

## Fit criterion

Run without the key, the judge sends nothing and prints the forecast and the digest; run with a digest that no longer matches what would be sent, it refuses; and the only run that sends is one given the digest the owner saw, with the key read from the owner's environment and never from the conversation.

## Applies to

| Type | Entity |
| --- | --- |
| feature | A decision model asks each page its schema's writing rules |

## Realization

`companygraph judge` in `bin/companygraph.mjs` without `TYPESAFE_API_KEY` prints the questions, the file list, the forecast and a 16-hex digest and sends nothing. With a key it still sends only on a yes typed at a terminal or `--consent <digest>`; a digest that no longer matches (a page edited, another endpoint or path, another model) is refused with `What would be sent has changed ... Nothing was sent`; a value that is not a digest is refused before anything is compared. The digest covers the endpoint, the model and every page's request, so a yes for another instance or an earlier run does not match. The key is read from the process environment. The skill tells the agent to ask the owner each run, naming the digest, and never to ask for or paste the key. The tests (`with no key, judge prints the questions and sends nothing`, `a page edited after the digest was shown refuses`, `a consent given for one endpoint does not send to another`, `a send to TypeSafe itself takes a yes typed at a terminal, never a piped one`) observe this. "Never from the conversation" is the skill's instruction and has no test.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `verify/judge.test.mjs` | verifies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/judge.test.mjs |
| `bin/companygraph.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/bin/companygraph.mjs |
| `agents/claude/skills/companygraph-judge/SKILL.md` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/agents/claude/skills/companygraph-judge/SKILL.md |

## References

| What | URL |
| --- | --- |
| The judge procedure | https://github.com/companygraph/meta-model/blob/main/agents/claude/skills/companygraph-judge/SKILL.md |
