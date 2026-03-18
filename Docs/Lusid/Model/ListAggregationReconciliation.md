# Finbourne.Sdk.Lusid.Model.ListAggregationReconciliation

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | [ListAggregationResponse](ListAggregationResponse.md) | Optional | *No description available.* |
| **Right** | [ListAggregationResponse](ListAggregationResponse.md) | Optional | *No description available.* |
| **Diff** | **List&lt;Dictionary&lt;string, Object&gt;&gt;** | Optional | *No description available.* |
| **DataSchema** | [ResultDataSchema](ResultDataSchema.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ListAggregationReconciliation(
    left: new ListAggregationResponse(...),  // optional
    right: new ListAggregationResponse(...),  // optional
    diff: ,  // optional
    dataSchema: new ResultDataSchema(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ListAggregationReconciliation>(json);
```


## Related Models

- [ListAggregationResponse](ListAggregationResponse.md)
- [ListAggregationResponse](ListAggregationResponse.md)
- [ResultDataSchema](ResultDataSchema.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

