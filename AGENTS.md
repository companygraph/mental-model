# CompanyGraph — working conventions

This repository is a CompanyGraph instance. The rules it is held to are vendored under
`meta/core/`, and `meta/core/CONVENTIONS.md` is the one to read before writing
anything here: one file per entity, a reference written as a canonical name, and a schema
for every type under the same folder.

The mechanical half of those rules is checked by CI, and locally by
`npx companygraph-meta-model check`. What no check reads is each schema's
`## Writing rules`, which an agent judges by reading them against the entity.

Everything below this line is this instance's own: how it is written, what it does not
claim, and where its facts are mastered.
