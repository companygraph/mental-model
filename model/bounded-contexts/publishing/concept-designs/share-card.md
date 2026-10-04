---
id: 01a10042-59ff-7870-9ee8-e8c5939fd306
source: Local
kind: value object
---

# Share card

> The image a link preview shows for a page, rendered from that page itself, with a stamp of what went into it so a card that no longer shows its page can be told without a browser.

## Attributes

| Attribute | Term | Type | Many | Description |
| --- | --- | --- | --- | --- |
| Page | | string | | The page it is rendered from |
| Image | | file | | `og.png` beside the page |
| Stamp | | hash | | `og.sha` beside it: a hash of the page, every local file it draws, the artifact it names included, and the frame it is rendered in |

## References

| What | URL |
| --- | --- |
| Implementation | https://github.com/companygraph/companygraph.github.io/blob/main/og-recipe.mjs |
| Implementation | https://github.com/companygraph/companygraph.github.io/blob/main/export-og.mjs |
| Implementation | https://github.com/companygraph/companygraph.github.io/blob/main/og-check.mjs |
