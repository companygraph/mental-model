---
id: 01a1312c-ba31-768b-ab88-cf336c1c4884
source: Local
kind: functional
modality: may
realization: Verified
---

# An instance may make its own ids under a declared pattern

> An instance may declare a pattern its ids follow instead of the tooling's own format, and then the tooling only checks the ids and never stamps one.

## Why

A company that already issues identifiers, in a register or a ticket system, keeps them rather than carrying a second id beside its own; a tooling that stamped its own format over them would make every page carry two.

## Fit criterion

With a pattern declared in the identifier page, the check holds every id to the pattern, and the backfill command refuses whole rather than writing an id of the tooling's own format.

## Applies to

| Type | Entity |
| --- | --- |
| feature | An instance is made and kept from one command |

## Realization

When `model/identifier.md` declares `format: pattern` with an anchored `pattern`, `lib/ids.mjs` reads it and the R18 check in `lib/checks.mjs` holds every page's id to the pattern; an unanchored pattern fails once at the identifier page and no page is held to it. `companygraph ids --backfill` refuses whole (exit 3, no page touched) when a pattern is declared and when the format is unreadable, so it never stamps a UUID over the company's own ids. Tests: `a pattern the identifier declares holds every id` (`verify/identifier.test.mjs`), `pattern holds ids to the pattern` (`verify/ids.test.mjs`), and `ids --backfill refuses whole when model/identifier.md declares a pattern` (`verify/cli.test.mjs`).

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `verify/identifier.test.mjs` | verifies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/identifier.test.mjs |
| `verify/cli.test.mjs` | verifies | https://github.com/companygraph/meta-model/blob/v0.95.0/verify/cli.test.mjs |
| `lib/ids.mjs` | satisfies | https://github.com/companygraph/meta-model/blob/v0.95.0/lib/ids.mjs |

## References

| What | URL |
| --- | --- |
| The identifier schema | https://github.com/companygraph/meta-model/blob/main/core/identifier-schema.md |
