---
id: 01a105f9-65d8-7839-9f6e-77f53f1c68ab
source: Local
kind: value object
refines: Reference
---

# Edge

> One edge of the snapshot, kept as the graph drew it.

## Attributes

| Attribute | Term | Type | Many | Description |
| --- | --- | --- | --- | --- |
| From | | id | | The entity whose page writes the name |
| To | | id | | The entity the name resolves to |
| Via | | string | | The field, column or heading that drew it |
| Qualifiers | | map | | The row's other cells, each a string |
