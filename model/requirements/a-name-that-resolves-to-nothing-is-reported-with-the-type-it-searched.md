---
id: 01a1312e-00d6-7ac7-b6a7-49be23dc9ce9
source: Local
kind: functional
modality: must
realization: Verified
---

# A name that resolves to nothing is reported with the type it searched

> The check reads every name a schema declares as a reference, and reports each one that resolves to nothing, with the type the declaration names and where the name was written.

## Why

A name resolves by the type its declaration names and never by a search over every type, so a writer told only that a name is unknown would look in the wrong folder; the type searched is what sends them to the right one.

## Fit criterion

A name that exists nowhere fails the page, saying what the column or field is declared to reference and that it names no entity; a name that exists under another type fails saying which type it is an entity of, and is never resolved there; and a name inside an owner resolves within that owner alone.

## Applies to

| Type | Entity |
| --- | --- |
| feature | Checks an instance runs |

## Realization

In `lib/checks.mjs` a declared reference or qualifier resolves against the type its declaration names alone. A name found nowhere fails the page with the declaration (for example `ref → identity`), the written value and `names no entity`; a name that is an entity of another type fails with `names an entity of type <type>, not <declared>`, and is not resolved there; an owned name resolves inside its owner, and a row naming another owner's entity fails as not one of the owner's own. Each message carries the file, the field or `Section.Column`, and the rule number R4. `verify/instance-checks.test.mjs` observes all three: a reference page naming nothing (`names no entity ... (R4)`), a qualifier naming another type's entity (`names an entity of type skill, not source ... (R4)`), and an owner's row naming an entity the owner does not own though the name resolves elsewhere. An optional `ref?` that matches nothing is held to nothing by design, which the criterion does not cover.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `verify/instance-checks.test.mjs` | verifies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/instance-checks.test.mjs |
| `lib/checks.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/lib/checks.mjs |

## References

| What | URL |
| --- | --- |
| The rules every page obeys | https://github.com/companygraph/meta-model/blob/main/core/CONVENTIONS.md |
