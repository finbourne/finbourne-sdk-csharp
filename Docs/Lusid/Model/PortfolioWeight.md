# Finbourne.Sdk.Lusid.Model.PortfolioWeight

Represents a portfolio and its target allocation weight.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Weight** | **decimal** | Required | The relative weight of the Portfolio compared to the other Portfolios specified, used to determine the allocation split between Portfolios when there are no Orders within the Block to allocate to. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PortfolioWeight(
    portfolioId: new ResourceId(...),  // required
    weight: 0.0d  // required — The relative weight of the Portfolio compared to the other Portfolios specified, used to determine the allocation split between Portfolios when there are no Orders within the Block to allocate to.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PortfolioWeight>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

