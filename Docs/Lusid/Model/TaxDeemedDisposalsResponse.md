# Finbourne.Sdk.Lusid.Model.TaxDeemedDisposalsResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FundId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Period** | [TaxAccountingPeriod](TaxAccountingPeriod.md) | Optional | *No description available.* |
| **Disposals** | [List&lt;TaxDeemedDisposalResponse&gt;](TaxDeemedDisposalResponse.md) | Optional | The deemed disposals at the end of the period. |
| **Vintages** | [List&lt;TaxReturnVintage&gt;](TaxReturnVintage.md) | Optional | The deemed-disposal vintages, one per period, that feed line D. |
| **Matrix** | [List&lt;TaxReturnSpreadInstalment&gt;](TaxReturnSpreadInstalment.md) | Optional | The seven-period spreading matrix for the vintages. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxDeemedDisposalsResponse(
    fundId: new ResourceId(...),  // optional
    period: new TaxAccountingPeriod(...),  // optional
    disposals: new List<TaxDeemedDisposalResponse>(),  // optional — The deemed disposals at the end of the period.
    vintages: new List<TaxReturnVintage>(),  // optional — The deemed-disposal vintages, one per period, that feed line D.
    matrix: new List<TaxReturnSpreadInstalment>()  // optional — The seven-period spreading matrix for the vintages.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxDeemedDisposalsResponse>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [TaxAccountingPeriod](TaxAccountingPeriod.md)
- [TaxDeemedDisposalResponse](TaxDeemedDisposalResponse.md) — used in `Disposals`
- [TaxReturnVintage](TaxReturnVintage.md) — used in `Vintages`
- [TaxReturnSpreadInstalment](TaxReturnSpreadInstalment.md) — used in `Matrix`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

