# Finbourne.Sdk.Lusid.Model.TaxPortfolioSyncStatus

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **LastTransactionAsAt** | **DateTimeOffset?** | Optional | The asAt the latest transaction was booked to the portfolio. Absent when the portfolio has no transactions. |
| **LastTaxAsAt** | **DateTimeOffset?** | Optional | The asAt the tax engine last processed the Fund, taken from its latest valuation point. Absent when no valuation point has been run. |
| **InSync** | **bool** | Required | True when the tax position is no older than the latest booked transaction, or the portfolio has no transactions. |
| **AssetClass** | **string** | Optional | The asset class of the portfolio&#39;s holdings where the holding data carries one. Optional. |
| **CountryOfDomicile** | **string** | Optional | The country of domicile of the portfolio&#39;s holdings where the holding data carries one. Optional. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxPortfolioSyncStatus(
    portfolioId: new ResourceId(...),  // required
    lastTransactionAsAt: DateTimeOffset.Now,  // optional — The asAt the latest transaction was booked to the portfolio. Absent when the portfolio has no transactions.
    lastTaxAsAt: DateTimeOffset.Now,  // optional — The asAt the tax engine last processed the Fund, taken from its latest valuation point. Absent when no valuation point has been run.
    inSync: true,  // required — True when the tax position is no older than the latest booked transaction, or the portfolio has no transactions.
    assetClass: "...",  // optional — The asset class of the portfolio&#39;s holdings where the holding data carries one. Optional.
    countryOfDomicile: "..."  // optional — The country of domicile of the portfolio&#39;s holdings where the holding data carries one. Optional.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxPortfolioSyncStatus>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

