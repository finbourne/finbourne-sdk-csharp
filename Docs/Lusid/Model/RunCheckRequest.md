# Finbourne.Sdk.Lusid.Model.RunCheckRequest

Exactly one dataset must be provided, matching the check definition's datasetSchema.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LusidEntityDataset** | [LusidEntityDataset](LusidEntityDataset.md) | Optional | *No description available.* |
| **LimitIndividualBreachesPerRule** | **int** | Optional | The maximum number of individual breaches to return per rule. Defaults to 100 if not specified. |
| **PortfolioHoldingDataset** | [PortfolioHoldingDataset](PortfolioHoldingDataset.md) | Optional | *No description available.* |
| **PortfolioTransactionDataset** | [PortfolioTransactionDataset](PortfolioTransactionDataset.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RunCheckRequest(
    lusidEntityDataset: new LusidEntityDataset(...),  // optional
    limitIndividualBreachesPerRule: 0,  // optional — The maximum number of individual breaches to return per rule. Defaults to 100 if not specified.
    portfolioHoldingDataset: new PortfolioHoldingDataset(...),  // optional
    portfolioTransactionDataset: new PortfolioTransactionDataset(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RunCheckRequest>(json);
```


## Related Models

- [LusidEntityDataset](LusidEntityDataset.md)
- [PortfolioHoldingDataset](PortfolioHoldingDataset.md)
- [PortfolioTransactionDataset](PortfolioTransactionDataset.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

