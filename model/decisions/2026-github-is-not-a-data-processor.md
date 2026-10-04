---
id: 01a107e5-e4d1-7a82-95e4-97815a4bdc15
source: Local
decided: 2026-10-04
kind: Data protection
status: Standing
by: Owner
upholds:
  - Run on what we publish
---

# GitHub is not one of our data processors

> GitHub serves companygraph.io's pages and sees the request that fetches each one, and we do not write it as a data processor: no processing agreement covers our account, and what GitHub keeps of a visit it keeps for its own purposes, so it is a recipient in its own right and not a party processing data on our behalf.

## The question

Core 0.60.0 gave this model the data-processor type, in the narrow meaning of GDPR Art. 4(8) and the Swiss DSG Art. 5 lit. k: a party that processes personal data on the company's behalf. The privacy page names three outside parties a visit can reach, GitHub, Anthropic and TypeSafe, and the question was whether each is a data processor in that meaning. For GitHub it had to be decided while the first processor pages were written, because the answer decides whether a privacy page built from the model names GitHub at all.

## Alternatives

| Option | Why not |
| --- | --- |
| Write GitHub as a data processor, citing its data protection agreement | The agreement forms part of the GitHub Customer Agreement, and our organization is on the free plan, so the page would cite a contract that does not cover us and claim a relation we do not have. |
| Widen the data-processor type to every recipient | The type was decided narrow on purpose, and a type that holds both processors and independent controllers stops answering the one question the law asks of it: who acts on our instructions. |

## Why

GitHub logs every Pages visitor's IP address for security purposes, whether or not the visitor is signed in. That purpose is GitHub's, not ours, so for what it keeps of a visit GitHub is a controller in its own right, which is the kind of recipient the narrow type leaves out. Without an agreement that makes it our processor, writing it as one would be the model saying more than is true.

## Consequences

The model names no host for companygraph.io's pages, and the privacy page keeps saying in its own words that GitHub serves them and sees each request. GitHub is the first real case for a type core does not have yet, an independent recipient, and the spec that adds it starts from this page. The call stays right for as long as the organization holds no GitHub agreement that makes GitHub its processor; if it takes one, GitHub gets a data-processor page and this call is revised.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| surface | companygraph.io website | | keeps naming GitHub in its own prose |

## References

| What | URL |
| --- | --- |
| GitHub Pages and the visitor data it logs | https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages |
| GitHub data protection agreement | https://github.com/customer-terms/github-data-protection-agreement |
| The spec that made the type narrow | https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-10-03-processors-and-stored-items-design.md |
