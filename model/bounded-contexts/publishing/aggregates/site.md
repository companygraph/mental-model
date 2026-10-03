---
id: 01a10042-596d-79f1-889c-4ff19146ce30
source: Local
root: Site
members:
  - Pin
  - Artifact
  - Derived region
  - Share card
decisions:
  - Every entity carries an id that outlives its name
---

# Site

> Everything a site publishes from a model is drawn at the commits its pins name, and each thing derived from an artifact matches the artifact it was derived from.

## Invariants

| Label | Invariant |
| --- | --- |
| INV-P1 | An artifact is read at exactly the commit its pin names; a local checkout whose HEAD is another commit is refused. |
| INV-P2 | An artifact is written only when its model was read whole; a read that stops leaves the committed file as it was. |
| INV-P3 | A committed artifact is, byte for byte, what its pin parses to. |
| INV-P4 | Every artifact carries the commit it was built from, and nothing is derived from one whose commit is not its pin's. |
| INV-P5 | Every derived region is what its renderer writes from the artifacts at their pins. |
| INV-P6 | A JSON-LD graph begins with its page's hand-written nodes and carries after them only the nodes its renderer owns; a graph with any other node there is refused, never rewritten. |
| INV-P7 | There is one id page for each entity of the company whose id is a UUID v7 and differs from its address, and the id folder holds nothing else. |
| INV-P8 | A share card's stamp is the hash of what went into it; a card whose page or drawn files have changed since is reported stale. |
| INV-P9 | Each sitemap entry is dated by its page's last commit. |
| INV-P10 | No command moves a pin; how far a pin is behind is reported and never fails the site. |

## Handled commands

| Command | Description |
| --- | --- |
| Move a pin | A person commits a new commit for a pin; then the artifacts, the derived regions, the pictures, the cards and the sitemap are rebuilt in that order |
| Build the artifacts | Reads each target at its pin through the parser and writes its artifact; refuses a checkout at another commit and stops at the first read that fails |
| Check the artifacts | Compares each committed artifact with what its pin parses to, and names the command to run where one differs |
| Render the derived regions | Writes every derived region from the artifacts; refuses an artifact that is missing or at another commit, and a JSON-LD graph it does not recognize |
| Render the share cards | Renders each card from its page in a browser and writes its stamp beside it |
| Date the sitemap | Dates each sitemap entry from its page's last commit |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/companygraph.github.io/blob/main/build/build.mjs |
| Implementation | https://github.com/companygraph/companygraph.github.io/blob/main/build/pages.mjs |
| Implementation | https://github.com/companygraph/companygraph.github.io/blob/main/build/jsonld.mjs |
| Implementation | https://github.com/robertblust/design/blob/main/lib/render/ids.mjs |
| Implementation | https://github.com/companygraph/companygraph.github.io/blob/main/og-check.mjs |
| Re-pin order | https://github.com/companygraph/companygraph.github.io/blob/main/pins.json |
