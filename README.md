# CompanyGraph — Mental Model

> CompanyGraph described in the vocabulary CompanyGraph publishes: the company behind the meta-model, as an instance of it.

The [reference instance](https://github.com/robertblust/mental-model) answered whether the vocabulary can hold a real company. It cannot answer whether the vocabulary holds a company that is not a person, because the company it describes is one — its vision, its strategies and its processes are all a person's, and nothing there shows which parts of the vocabulary need a person behind them and which do not. This instance has no people in it, and that is what separates the two. It is also the first instance the [meta-model](https://github.com/companygraph/meta-model)'s tooling created rather than a person laid out by hand; its design is the meta-model's [CompanyGraph instance spec](https://github.com/companygraph/meta-model/blob/main/docs/superpowers/specs/2026-09-21-companygraph-instance-design.md).

```text
.companygraph/manifest.json    which units this vendors, and a hash per vendored file
meta/core/                     core at the release .companygraph/manifest.json names, copied whole and never edited here
conventions/                   the family's shared conventions, vendored at the release conventions.json names
model/                         the company — everything under here is an entity, nothing else is
  identity.md                  who the company is, and where it can be found
  vision.md                    the future it works toward
  sources/                     where each page's facts are mastered
  values/                      what it will and will not do
  strategic-objectives/        what must become true for the vision to be reached
  strategies/                  how one gets reached, and what the route rules out
  surfaces/                    one file per place the model is published
  roles/                       the seats its work is done from, each naming no holder
  processes/                   its one kind of work, phase by phase
AGENTS.md                      this instance's own rules; every modeling rule is in meta/core/CONVENTIONS.md
```

**No person is described here.** CompanyGraph is operated by the company of one the reference instance describes, and that is where the person is. Writing a profile here would put one canonical name in two instances with two sets of facts behind it, and the second set would go stale without a sound, so no `profile`, `skill`, `experience` or `proficiency-level` is written in this repository. Core declares those types without obliging an instance to populate them, and this is the instance that exercises that. A `role` is written and a person is not, because a role is a seat: it names no holder, and who fills one is a fact this repository does not carry.

The content is mastered here — `source: Local`, corrected in this repository and nowhere else — and what it says is drawn from prose that is already published: the organization profile on GitHub, the pages of companygraph.io, the specs in the meta-model and the introduction talk. Nothing is invented, and a claim that cannot be traced to one of those does not go in.

## License

[CC BY 4.0](LICENSE) for everything written here — the model and the documentation beside it. Use it, quote it, build on it; credit it. The prose is the artifact, which is why this is a content license rather than a code license.

`meta/core/` is not written here: it is CompanyGraph core, vendored at the release `.companygraph/manifest.json` names, and stays under its own [Apache 2.0](meta/core/LICENSE). `conventions/` is vendored the same way, from robertblust/conventions at the release `conventions.json` names, and is edited there.
