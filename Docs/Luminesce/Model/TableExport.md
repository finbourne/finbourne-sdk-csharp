# Finbourne.Sdk.Luminesce.Model.TableExport

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TableName** | **string** | Optional | *No description available.* |
| **Columns** | [List&lt;ExportColumn&gt;](ExportColumn.md) | Optional | *No description available.* |
| **Grouping** | [ExportGrouping](ExportGrouping.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new TableExport(
    tableName: "...",  // optional
    columns: new List<ExportColumn>(),  // optional
    grouping: new ExportGrouping(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TableExport>(json);
```

- [ExportColumn](ExportColumn.md)
- [ExportGrouping](ExportGrouping.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

