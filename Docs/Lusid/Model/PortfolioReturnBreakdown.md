# Finbourne.Sdk.Lusid.Model.PortfolioReturnBreakdown

A list of Composite Breakdowns.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **RateOfReturn** | **decimal** | Optional | The return number. |
| **OpeningMarketValue** | **decimal?** | Optional | The opening market value. |
| **ClosingMarketValue** | **decimal?** | Optional | The closing market value. |
| **Weight** | **decimal** | Optional | The weight of the constituent into the composite. |
| **ConstituentsInTheComposite** | **int** | Optional | The number of members in the Composite on the given day. |
| **ConstituentsMissing** | **int** | Optional | The number of the constituents which have a missing return on that day. |
| **Currency** | **string** | Optional | The currency of the portfolio. |
| **OpenFxRate** | **decimal** | Optional | The opening fxRate which is used in calculation. |
| **CloseFxRate** | **decimal** | Optional | The closing fxRate which is used in calculation. |
| **LocalRateOfReturn** | **decimal?** | Optional | The rate of return in the local currency. |
| **LocalOpeningMarketValue** | **decimal?** | Optional | The opening market value in the local currency. |
| **LocalClosingMarketValue** | **decimal?** | Optional | The closing market value in the local currency. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PortfolioReturnBreakdown(
    portfolioId: new ResourceId(...),  // required
    rateOfReturn: 0.0d,  // optional — The return number.
    openingMarketValue: 0.0d,  // optional — The opening market value.
    closingMarketValue: 0.0d,  // optional — The closing market value.
    weight: 0.0d,  // optional — The weight of the constituent into the composite.
    constituentsInTheComposite: 0,  // optional — The number of members in the Composite on the given day.
    constituentsMissing: 0,  // optional — The number of the constituents which have a missing return on that day.
    currency: "...",  // optional — The currency of the portfolio.
    openFxRate: 0.0d,  // optional — The opening fxRate which is used in calculation.
    closeFxRate: 0.0d,  // optional — The closing fxRate which is used in calculation.
    localRateOfReturn: 0.0d,  // optional — The rate of return in the local currency.
    localOpeningMarketValue: 0.0d,  // optional — The opening market value in the local currency.
    localClosingMarketValue: 0.0d  // optional — The closing market value in the local currency.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PortfolioReturnBreakdown>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

