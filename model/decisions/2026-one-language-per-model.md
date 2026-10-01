---
id: 01a0f588-3c5a-7cf9-a128-86d8a38d6e13
source: Local
decided: 2026-10-01
kind: Vocabulary
status: Standing
by: Owner
serves:
  - A company we have never met keeps its own model
---

# A model is written in one language

> A model is written in the one language its localization page names, and is never translated inside itself; another language is a rendering of it, not a second copy in it.

## The question

Whether one entity carries its name and prose in several languages. An adopter asked in meta-model #195 for a model written in German and for one model kept in seven languages, and v0.66.0 gave every page a section for each translated language. It had to be decided again on October 1, 2026, when the rule was tried on a profile and the page carried a second copy of itself, before any instance had declared a translated language.

## Alternatives

| Option | Why not |
| --- | --- |
| A section per language at the foot of each page | A second copy of the page under English headings, every table repeated whole to keep its rows aligned, and a declared language binding every page of every type. |
| A sibling file per language | One entity becomes two texts that have to be kept the same. |
| A column per language in each table | Every table grows a column for every language it is read in. |
| The translated languages declared per type | Every page of a listed type is still two texts, and the model is half in one language and half in two. |

## Why

A model is kept in one language, as UML, SysML and an XML schema are: the vocabulary is English, and the content is in whatever language the company thinks in. Translating content is what a documentation system or a translation tool does, and doing it inside the model doubled every page it touched.

## Consequences

`model/localization.md` names the model's language in `locale`, and R19 and its checks are gone. A company writes its model in German if German is what it thinks in; one that needs seven languages renders them outside the model. Given up: a chat answering in Polish from Polish text the model holds. The call stays right for as long as a reader in another language is served by a rendering, and no adopter needs two languages to carry the same claim with equal standing inside one model.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| localization | Languages | | changed it |
| feature | Checks an instance runs | | changed it |
| role | Translator | | changed it |

## References

| What | URL |
| --- | --- |
| The issue | https://github.com/companygraph/meta-model/issues/195 |
| The specification | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-10-01-one-language-per-model-design.md |
| The specification it replaces | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-09-30-a-model-in-several-languages-design.md |
