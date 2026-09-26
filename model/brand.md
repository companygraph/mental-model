---
source: Local
---

# CompanyGraph

> Everything a company knows, in one graph that its people and its agents read alike.

## Mark

The mark is two squares joined by a line, two entities and the edge between them, set in the accent color on the ground, and its master is `favicon.svg` in the site's repository; every other render, a tile a host is handed, a slide's corner, is made from that file and never drawn again. The mark's colors are the design tokens' ground and accent.

- A tile is a full-bleed square with no rounded corner, because the host rounds it and a transparent corner shows as a checkerboard.
- The mark fills about 60% of the tile, so it survives a circular crop.
- A change to the mark is made in the favicon first and rendered everywhere else after.
- Where a render carries values other than the tokens', the favicon included, the tokens are the master and the render follows.

## Color

| Name | Means | Never |
| --- | --- | --- |
| `--c-weak` | A candidate: considered, not accepted | Text, a border or an outline on its own, in either theme |
| `--c-mid` | Anything interactive: a link, a control, the brand accent | The resolved thing, which would then read as still open |
| `--c-firm` | The resolved thing: the thesis, the current page | A link, which would then read as settled |
| `--c-flag` | A reversal, at most once per page | Decoration |
| `--c-sum` | A conclusion, what a section's figures add up to, as the line of a conclusion and at most once per section | Text |
| `--c-path` | Where you are and how you got here: the ancestors of the focused node and the line through them | The resolved thing, which only happens to look alike |

## Typography

| Face | Job |
| --- | --- |
| Instrument Sans | Prose: the body of every page and every deck |
| Plex Mono | The ledger and the chrome: the footer, the stage and a deck's transport |
| Bricolage Grotesque | A section's mark: the small heading that names a principle, a seat or a surface |

## Voice

| Trait | Means | Never |
| --- | --- | --- |
| Plain | We say what a type holds in the words a person who runs a company uses for it | An adjective that sells: nothing here is powerful, seamless or robust |
| Shown | We claim what an instance shows, and we name the instance | A count of types, entities or adopters, which moves the day it is written |
| Cause first | We say why a rule exists before we say what it checks | A rule with no reason beside it |
| Adoptable | We say how to do it without us, in the same sentence that says what it is | A step that only we can take |
| Read twice | We would rather be read twice than skimmed once: one idea per sentence, the point in the first | A header that segments a text which fits on a screen |

## References

| What | URL |
| --- | --- |
| Design tokens | https://github.com/robertblust/design/blob/main/blocks/tokens.css |
| Mark | https://github.com/companygraph/companygraph.github.io/blob/main/favicon.svg |
| Rulebook of the voice | https://github.com/robertblust/conventions/blob/main/conventions/WRITING.md |
| Typefaces, as the pages set them | https://github.com/robertblust/design/blob/main/blocks/reset.css |
