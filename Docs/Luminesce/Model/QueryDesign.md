# Finbourne.Sdk.Luminesce.Model.QueryDesign

Representation of a \"designable Query\" suitable for formatting to SQL or being built from compliant SQL.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TableName** | **string** | Required | Name of the table being designed |
| **Alias** | **string** | Optional | Alias for the table in the generated SQL, if any |
| **Fields** | [List&lt;FieldDesign&gt;](FieldDesign.md) | Required | Fields to be selected, aggregated over and/or filtered on |
| **JoinedTables** | [List&lt;JoinedTableDesign&gt;](JoinedTableDesign.md) | Optional | Joined in table to the main TableName / Alias |
| **OrderBy** | [List&lt;OrderByTermDesign&gt;](OrderByTermDesign.md) | Optional | Order By clauses to apply |
| **Limit** | **int?** | Optional | Row limit to apply, if any |
| **Offset** | **int?** | Optional | Row offset to apply, if any |
| **Warnings** | **List&lt;string&gt;** | Optional | Any warnings to show the user when converting from SQL to this representation |
| **AvailableFields** | [List&lt;AvailableField&gt;](AvailableField.md) | Optional | Fields that are known to be available for design when parsing SQL |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new QueryDesign(
    tableName: "...",  // required — Name of the table being designed
    alias: "...",  // optional — Alias for the table in the generated SQL, if any
    fields: new List<FieldDesign>(),  // required — Fields to be selected, aggregated over and/or filtered on
    joinedTables: new List<JoinedTableDesign>(),  // optional — Joined in table to the main TableName / Alias
    orderBy: new List<OrderByTermDesign>(),  // optional — Order By clauses to apply
    limit: 0,  // optional — Row limit to apply, if any
    offset: 0,  // optional — Row offset to apply, if any
    warnings: ,  // optional — Any warnings to show the user when converting from SQL to this representation
    availableFields: new List<AvailableField>()  // optional — Fields that are known to be available for design when parsing SQL
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<QueryDesign>(json);
```

- [FieldDesign](FieldDesign.md) — used in `Fields`
- [JoinedTableDesign](JoinedTableDesign.md) — used in `JoinedTables`
- [OrderByTermDesign](OrderByTermDesign.md) — used in `OrderBy`
- [AvailableField](AvailableField.md) — used in `AvailableFields`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

