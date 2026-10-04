---
id: 01a0faae-d24f-77ec-b7ad-bc05c556c781
source: Local
kind: value object
refines: Reference
---

# Edge

> One entity joined to another because a field, a table column or a grouped heading its schema declares as a reference names it. Two edges with the same ends and the same origin are the same edge.

## Attributes

| Attribute | Term | Type | Many | Description |
| --- | --- | --- | --- | --- |
| From | | id | | The entity whose page writes the name |
| To | | id | | The entity the name resolves to |
| Via | | string | | The field, `<Section>.<Column>` or `<Section>.<Heading>` that drew it |
| Qualifiers | | map | | The row's other cells, which describe the edge and draw none of their own, each a string |

## Relations

| Concept | Cardinality | As |
| --- | --- | --- |
| Declaration | one | drawn by |
