# Finbourne.Sdk.Lusid.Model.EligibleCollateralRow

One class of eligible collateral and how it is valued, as stored on a schedule.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The stable key the row is referred to by. Unique within the schedule. |
| **Description** | **string** | Optional | A description of the row. Optional. |
| **Selector** | [EligibleCollateralAssetSelector](EligibleCollateralAssetSelector.md) | Required | *No description available.* |
| **ValuationPercentage** | **decimal** | Required | The fraction of an asset&#39;s value that is accepted as collateral, for example 0.95 for 95%. Greater than 0 and at most 1. |
| **FxHaircut** | **decimal?** | Optional | The further fraction deducted when the asset&#39;s currency is not the agreement&#39;s base currency, so that the effective valuation percentage is ValuationPercentage * (1 - FxHaircut). At least 0 and less than 1. Not allowed for a BaseCurrencyCash selector. Optional. |
| **MinResidualMaturityYears** | **decimal?** | Optional | The inclusive lower bound of the residual maturity in years that the row applies to. Only allowed for an Instrument selector. Optional. |
| **MaxResidualMaturityYears** | **decimal?** | Optional | The exclusive upper bound of the residual maturity in years that the row applies to. Only allowed for an Instrument selector. Optional. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EligibleCollateralRow(
    code: "...",  // required — The stable key the row is referred to by. Unique within the schedule.
    description: "...",  // optional — A description of the row. Optional.
    selector: new EligibleCollateralAssetSelector(...),  // required
    valuationPercentage: 0.0d,  // required — The fraction of an asset&#39;s value that is accepted as collateral, for example 0.95 for 95%. Greater than 0 and at most 1.
    fxHaircut: 0.0d,  // optional — The further fraction deducted when the asset&#39;s currency is not the agreement&#39;s base currency, so that the effective valuation percentage is ValuationPercentage * (1 - FxHaircut). At least 0 and less than 1. Not allowed for a BaseCurrencyCash selector. Optional.
    minResidualMaturityYears: 0.0d,  // optional — The inclusive lower bound of the residual maturity in years that the row applies to. Only allowed for an Instrument selector. Optional.
    maxResidualMaturityYears: 0.0d  // optional — The exclusive upper bound of the residual maturity in years that the row applies to. Only allowed for an Instrument selector. Optional.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EligibleCollateralRow>(json);
```

- [EligibleCollateralAssetSelector](EligibleCollateralAssetSelector.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

