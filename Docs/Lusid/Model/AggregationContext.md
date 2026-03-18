# Finbourne.Sdk.Lusid.Model.AggregationContext

Aggregation context node. Whilst the market and pricing nodes concern themselves with which models are used and where the market data comes from, the aggregation  context determines how data is aggregated together. This controls the behaviour of the grouping and sql-like engine at the back of the valuation. For instance,  it controls conversion of currencies and whether the sql-like engine behaves more like ANSI or MySql SQL.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Options** | [AggregationOptions](AggregationOptions.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AggregationContext(
    options: new AggregationOptions(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AggregationContext>(json);
```


## Related Models

- [AggregationOptions](AggregationOptions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

