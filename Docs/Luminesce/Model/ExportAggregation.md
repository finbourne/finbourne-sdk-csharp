# Finbourne.Sdk.Luminesce.Model.ExportAggregation

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ColId** | **string** | Required | *No description available.* |
| **AggFunc** | **ExportAggregationFunction** | Optional | *No description available.* |
| **Placement** | **ExportAggregationPlacement** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new ExportAggregation(
    colId: "...",  // required
    aggFunc: ,  // optional
    placement:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExportAggregation>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

