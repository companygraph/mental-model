---
id: 01a0fd96-9ca4-705d-921e-246153fb78c3
source: Local
modality: must
---

# A state is read again before it is relied on

> A state — a branch, a pull request, a check, a release, another session's work — is read again from its source in the conversation that relies on it; an earlier reading, or a session's transcript where the session can be asked, is not the state.

## Why

Several sessions and people move the same repositories at once, so a state read earlier in a conversation may have moved by the time it is acted on, and a transcript says what a session set out to do rather than what it did. Fetching main before a merge is this rule.

## Applies to

| Type | Entity | Owner |
| --- | --- | --- |
| role | Surveyor | |
| process | Deciding | |
| phase | Integrate | Delivery |
| phase | Integrate | Contribution |
