# Finbourne.Sdk.Luminesce.Model.ExportGrouping

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **GroupKeys** | **List&lt;string&gt;** | Optional | *No description available.* |
| **DateParts** | **Dictionary&lt;string, string&gt;** | Optional | *No description available.* |
| **Aggregations** | [List&lt;ExportAggregation&gt;](ExportAggregation.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new ExportGrouping(
    groupKeys: ,  // optional
    dateParts: ,  // optional
    aggregations: new List<ExportAggregation>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExportGrouping>(json);
```

- [ExportAggregation](ExportAggregation.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

