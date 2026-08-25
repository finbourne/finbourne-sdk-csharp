# Finbourne.Sdk.Lusid.Model.PortfolioHoldingDataset

Contains the run-time parameters that are appropriate for check definitions  with datasetSchema.type = \"PortfolioContents\"
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsAt** | **DateTimeOffset?** | Optional | The asAt date to fetch the data. Nullable. Defaults to latest. |
| **EffectiveAt** | **DateTimeOffset?** | Optional | The effectiveAt date to fetch the data. Nullable. Defaults to latest. |
| **PortfolioScope** | **string** | Optional | The scope of the portfolios whose holdings to check. Nullable. Every scope is checked if not provided. |
| **PortfolioSelectorAttribute** | **string** | Optional | An attribute (field name or propertyKey) to use to narrow down the portfolios whose holdings are checked. |
| **PortfolioSelectorValue** | **string** | Optional | The value of the above attribute used to narrow down the portfolios. |
| **HoldingSelectorAttribute** | **string** | Optional | An attribute (field name, propertyKey or sub-holding key) to use to narrow down the holdings checked  within those portfolios. |
| **HoldingSelectorValue** | **string** | Optional | The value of the above attribute used to narrow down the holdings. |
| **ByTaxlots** | **bool** | Optional | Whether to expand holdings to their underlying tax lots. Defaults to false. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PortfolioHoldingDataset(
    asAt: DateTimeOffset.Now,  // optional — The asAt date to fetch the data. Nullable. Defaults to latest.
    effectiveAt: DateTimeOffset.Now,  // optional — The effectiveAt date to fetch the data. Nullable. Defaults to latest.
    portfolioScope: "...",  // optional — The scope of the portfolios whose holdings to check. Nullable. Every scope is checked if not provided.
    portfolioSelectorAttribute: "...",  // optional — An attribute (field name or propertyKey) to use to narrow down the portfolios whose holdings are checked.
    portfolioSelectorValue: "...",  // optional — The value of the above attribute used to narrow down the portfolios.
    holdingSelectorAttribute: "...",  // optional — An attribute (field name, propertyKey or sub-holding key) to use to narrow down the holdings checked  within those portfolios.
    holdingSelectorValue: "...",  // optional — The value of the above attribute used to narrow down the holdings.
    byTaxlots: true  // optional — Whether to expand holdings to their underlying tax lots. Defaults to false.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PortfolioHoldingDataset>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

