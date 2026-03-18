# Finbourne.Sdk.Lusid.Model.SpecificHoldingPricingInfo

Allows a user to specify fallbacks/overrides using Holding fields for sources that match a particular DependencySourceFilter.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DependencySourceFilter** | [DependencySourceFilter](DependencySourceFilter.md) | Required | *No description available.* |
| **Field** | **string** | Required | The Holding field which the fallback/override should use to create a price quote. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SpecificHoldingPricingInfo(
    dependencySourceFilter: new DependencySourceFilter(...),  // required
    field: "..."  // required — The Holding field which the fallback/override should use to create a price quote.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SpecificHoldingPricingInfo>(json);
```


## Related Models

- [DependencySourceFilter](DependencySourceFilter.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

