---
id: 01a0fd96-d8d5-7673-8274-8b2b6e3eca58
source: Local
modality: must
---

# One session holds a piece of shared work

> Before shared work — a release, a re-pin, a re-sync, a change across repositories — a session checks for open pull requests, branches and tags and asks the running sessions; the first to claim it holds it, says so, and tells the others when it is done, and no one else opens a parallel change.

## Why

Several sessions work in our repositories at once, and the Surveyor already works from the list of them and what each is doing, and Carry tells the sessions a change touches what changed. Without a claim made before acting, two sessions cut the same release or overwrite each other's branch.

## Applies to

| Type | Entity | Owner |
| --- | --- | --- |
| seat | Surveyor | |
| phase | Integrate | Delivery |
| phase | Carry | Deciding |
