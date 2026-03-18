# Finbourne.Sdk.Luminesce.Model.TableLineage

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ColumnLineage** | [List&lt;Lineage&gt;](Lineage.md) | Optional | *No description available.* |
| **WholeTableLineage** | [Lineage](Lineage.md) | Optional | *No description available.* |
| **FailureReason** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new TableLineage(
    columnLineage: new List<Lineage>(),  // optional
    wholeTableLineage: new Lineage(...),  // optional
    failureReason: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TableLineage>(json);
```


## Related Models

- [Lineage](Lineage.md)
- [Lineage](Lineage.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

