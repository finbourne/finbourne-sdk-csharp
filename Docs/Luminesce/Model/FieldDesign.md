# Finbourne.Sdk.Luminesce.Model.FieldDesign

Treatment of a single field within a QueryDesign
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | Name of the Field (column name, constant, complex expression, etc.) |
| **TableAlias** | **string** | Optional | Alias of the Table the field belongs to |
| **Alias** | **string** | Optional | Alias if any (if none the Name is used) |
| **DataType** | **DataType** | Optional | *No description available.* |
| **ShouldSelect** | **bool** | Optional | Should this be selected? False would imply it is only being filtered on. Ignored when Aggregations are present |
| **Filters** | [List&lt;FilterTermDesign&gt;](FilterTermDesign.md) | Optional | Filter clauses to apply to this field (And&#39;ed together) |
| **Aggregations** | [List&lt;Aggregation&gt;](Aggregation.md) | Optional | Aggregations to apply (as opposed to simply selecting) |
| **IsExpression** | **bool** | Optional | Is this field an expression |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new FieldDesign(
    name: "...",  // required — Name of the Field (column name, constant, complex expression, etc.)
    tableAlias: "...",  // optional — Alias of the Table the field belongs to
    alias: "...",  // optional — Alias if any (if none the Name is used)
    dataType: ,  // optional
    shouldSelect: true,  // optional — Should this be selected? False would imply it is only being filtered on. Ignored when Aggregations are present
    filters: new List<FilterTermDesign>(),  // optional — Filter clauses to apply to this field (And&#39;ed together)
    aggregations: new List<Aggregation>(),  // optional — Aggregations to apply (as opposed to simply selecting)
    isExpression: true  // optional — Is this field an expression
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FieldDesign>(json);
```

- [FilterTermDesign](FilterTermDesign.md) — used in `Filters`
- [Aggregation](Aggregation.md) — used in `Aggregations`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

