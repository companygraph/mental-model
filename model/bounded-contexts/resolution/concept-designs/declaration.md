---
id: 01a0faae-d24f-746e-9e5a-feb86a53dde1
source: Local
kind: value object
refines: Schema
---

# Declaration

> What a schema says one field, column or heading is: a reference that must resolve, a reference that may name nothing, or a qualifier, each pointing at one type. Anything a schema does not declare this way is a fact and is never resolved.

## Attributes

| Attribute | Term | Type | Many | Description |
| --- | --- | --- | --- | --- |
| Form | | string | | `ref`, `ref?` or `qualifier` |
| Target | | string | | The type a written name is looked for in |
| By | | string | | For `ref → by <Column>`, the column of the same row that names the type |
| In | | string | | For `… in <Owner>`, the column of the same row that names the owner |
