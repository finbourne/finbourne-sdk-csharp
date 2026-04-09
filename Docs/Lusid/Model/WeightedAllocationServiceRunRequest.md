# Finbourne.Sdk.Lusid.Model.WeightedAllocationServiceRunRequest

The request body for the RunAllocationServiceWithWeights endpoint.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PlacementIds** | [List&lt;ResourceId&gt;](ResourceId.md) | Required | The set of Placement IDs to allocate. |
| **PortfolioWeights** | [List&lt;PortfolioWeight&gt;](PortfolioWeight.md) | Optional | The set of Portfolios and their associated weights to use for allocation. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WeightedAllocationServiceRunRequest(
    placementIds: new List<ResourceId>(),  // required — The set of Placement IDs to allocate.
    portfolioWeights: new List<PortfolioWeight>()  // optional — The set of Portfolios and their associated weights to use for allocation.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WeightedAllocationServiceRunRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md) — used in `PlacementIds`
- [PortfolioWeight](PortfolioWeight.md) — used in `PortfolioWeights`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

