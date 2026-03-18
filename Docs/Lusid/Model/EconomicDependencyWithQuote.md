# Finbourne.Sdk.Lusid.Model.EconomicDependencyWithQuote

Container class pairing economic dependencies and quote data
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EconomicDependency** | [EconomicDependency](EconomicDependency.md) | Required | *No description available.* |
| **MetricValue** | [MetricValue](MetricValue.md) | Required | *No description available.* |
| **ScaleFactor** | **decimal?** | Optional | Scale factor for the quote - this can be null, in which case we default to 1. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EconomicDependencyWithQuote(
    economicDependency: new EconomicDependency(...),  // required
    metricValue: new MetricValue(...),  // required
    scaleFactor: 0.0d  // optional — Scale factor for the quote - this can be null, in which case we default to 1.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EconomicDependencyWithQuote>(json);
```


## Related Models

- [EconomicDependency](EconomicDependency.md)
- [MetricValue](MetricValue.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

