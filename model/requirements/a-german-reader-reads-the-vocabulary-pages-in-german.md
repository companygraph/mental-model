---
id: 01a1312d-9384-77bc-a0e9-c22318bb2902
source: Local
kind: functional
modality: should
realization: Released
---

# A German reader reads the vocabulary pages in German

> The pages around the vocabulary read in Swiss Standard German when the reader switches to it, while the schemas the pages draw stay in the one language the model is written in.

## Why

The person behind the family is Swiss, and a reader in Zürich or Bern is a reader the pages are written for. The schemas themselves are not translated, because a model is written in one language and a schema translated would be a second schema; that is the reason to depart, stated on the page beside the figure.

## Fit criterion

Switched to German, the model page around the figure and the stage's own labels read in Swiss Standard German, the schemas it draws stay in English, and the page says so beside them.

## Applies to

| Type | Entity |
| --- | --- |
| feature | The vocabulary on the web |

## Realization

The site's `model/index.html` carries a German value on every label, note and caption around the figure, including the stage's own buttons and hints, and a note saying the page is generated from the core and the packs at the commit beside the figure "in der einen Sprache, in der das Modell geschrieben ist". The schemas are drawn from `model.json` and are not translated. The site's `verify` suite loads the model page, switches to German, checks that "Das Modell", "gezeichnet" and "Wie man es liest" show and the English heading is gone, then checks that every element carrying a German value shows exactly it and that switching back restores the English. No test asserts that the drawn schema names stay English or that the note beside the figure says so; that rests on the page's text.

## Evidence

| What | Shows | URL |
| --- | --- | --- |
| `model/index.html` | satisfies | https://github.com/companygraph/companygraph.github.io/blob/3f8e4a25f599cc0e3c77cce8cce17e585d7a6b0e/model/index.html |
| `verify/check.mjs` | satisfies | https://github.com/companygraph/companygraph.github.io/blob/3f8e4a25f599cc0e3c77cce8cce17e585d7a6b0e/verify/check.mjs |
| `verify/pages.mjs` | satisfies | https://github.com/robertblust/design/blob/v0.158.2/verify/pages.mjs |

## References

| What | URL |
| --- | --- |
| The model page | https://companygraph.io/model/ |
